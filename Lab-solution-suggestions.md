These are our suggestions for solutions to the tasks at the [Labs-page](https://github.com/sesam-community/wiki/wiki/Labs).

# Lab 1
```
{
  "_id": "lab-crm-person",
  "type": "pipe",
  "source": {
    "type": "dataset",
    "dataset": "crm-person"
  },
  "transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"],
        ["add", "FullName",
          ["concat", "_S.FirstName", " ", "_S.LastName"]
        ]
      ]
    }
  }
}
```

# Lab 2
```
{
  "_id": "lab2-azure-person",
  "type": "pipe",
  "source": {
    "type": "dataset",
    "dataset": "azure-person"
  },
  "transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"],
        ["remove", "SSN"],
        ["add", "Birthday",
          ["substring", 0, 6, "_S.SSN"]
        ]
      ]
    }
  }
}
```

# Lab 3
```
{
  "_id": "lab3-global-person",
  "type": "pipe",
  "source": {
    "type": "merge",
    "datasets": ["crm-person cp", "firebase-person fp", "azure-person ap", "salesforce-userprofile sup"],
    "equality": [
      ["eq", "cp.SSN-ni", "ap.$ids"],
      ["eq", "cp.SSN-ni", "fp.$ids"],
      ["eq", "cp.Username", "sup.Username"]
    ],
    "identity": "first",
    "version": 2
  },
  "transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"]
      ]
    }
  }
}
```

Above is our preferred way of solving Lab 3, but you can also do this without using the SSN namespace identifier. You can match on any properties that you know will have matching values. But there is value in using namespace identifiers as for equality checks and we recommend reading up on namespace identifiers in the [Getting started with Sesam guide](https://github.com/sesam-community/wiki/wiki/Getting-started#6312-Namespace-identifiers) or in the [documentation](https://docs.sesam.io/DTLReferenceGuide.html#namespaces).

Below is an example of merging datasets without namespace identifiers. In this example we remove the namespace in "firebase-person"'s "_id" to match the new substring with "SSN" in "crm-person":
```
{
  "_id": "lab3-global-person",
  "type": "pipe",
  "source": {
    "type": "merge",
    "datasets": ["crm-person cp", "firebase-person fp", "azure-person ap", "salesforce-userprofile sup"],
    "equality": [
      ["eq", "cp.SSN", "ap.SSN"],
      ["eq", "cp.SSN",
        ["substring", 16, "fp._id"]
      ],
      ["eq", "cp.Username", "sup.Username"]
    ],
    "identity": "first",
    "version": 2
  },
  "transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"]
      ]
    }
  }
}
```

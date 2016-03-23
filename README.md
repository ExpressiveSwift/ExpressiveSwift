# ExpressiveSwift

<img src="https://img.shields.io/badge/Swift-2-brightgreen.svg" alt="Swift 2"> 

Welcome!

ExpressiveSwift is a collection of µ-frameworks, each one solving a specific problem with straightforward, concise, readable and safe code.

We value simplicity and pragmatism. We try to adopt Swift paradigms and idioms where it makes sense, but we do _not_ endorse functional programming extravaganza or veering into the darkest corners of the language.


## Versions and statuses

We follow [semantic versioning](http://semver.org) and additionally assign a production readiness status to each µ-framework:

* stable: (1) is used in multiple production apps, (2) is well-documented, (3) has reached a stable API we're generally satisfied with. This is a requirement to release version 1.0.0.

* beta: (1) is used in multiple production apps, (2) documentation effort is in progress, (3) may still undergo heavy or incompatible changes.

* alpha: (1) seems to work, (2) is successfully used by an app under development, (3) can be adopted if you don't mind digging into and debugging the code of the framework occasionally, (4) may undergo radical changes.

* development: not ready for consumption yet, unless you're ready to join the development effort.


## Our µ-frameworks

* [ExpressiveCasting](https://github.com/ExpressiveSwift/ExpressiveCasting) (beta): Defensive parsing of untyped and potentially untrusted data (JSON APIs, User Defaults and such)

        // ExpressiveCasting provides wordy functions...
        name  = NonEmptyStringValue(raw["name") ?? "Unnamed"
        price = IntValue(raw["age"])
        url   = URLValue(raw["url"])
        photos = JSONConvertibleObjectsArrayValue(raw["photos"])

        // ...and concise operators; pick your poison!
        name  = raw["name"]~~~ ?? "Unnamed"
        price = raw["price"]~~~
        url   = raw["url"]~~~ 
        photos = raw["photos"]~~~


## Other small frameworks we recommend

* [Cartography](https://github.com/robb/Cartography): An expressive DSL for autolayout constraints

        constrain(view1, view2) { view1, view2 in
            view1.width   == (view1.superview!.width - 50) * 0.5
            view2.width   == view1.width - 50
            view1.height  == 40
            view2.height  == view1.height
            view1.centerX == view1.superview!.centerX
            view2.centerX == view1.centerX

            view1.top >= view1.superview!.top + 20
            view2.top == view1.bottom + 20
        }

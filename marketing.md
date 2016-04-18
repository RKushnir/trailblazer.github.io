##

## Community

Gitter channel
Newsletter


## Trailblazer brings more abstraction layers

Abstraction layers simplify implementing sets of functionality, allowing for separation of concerns.

While this might sound like more technical complexity, Trailblazer identifies the workflows of processing web requests from dispatching to rendering a response and provides a place for each step.

The new abstraction layers are more intuitive: developers now understand where to put code.

## Trailblazer picks you up, where Rails left off

Rails is a popular web framework for ruby. It is used as a teaching aid to teach people of all ages how to program web applications.

Rails does an awesome job at introducing the basics to developers, however, code can grow and Rails code can be a bit unwieldy once it becomes a monolith. Trailblazer provides that next piece of the puzzle, to refactor your applications into lean trailblazers.



"We never had the time to refactor that..."

In a low-level framework like Rails you waste an incredible amount of time for thinking about where goes what, and how to make certain code apply to a specific environment, only.

Trailblazer takes away most of those decisions.

1. You structure your code by use cases.
2. You know where validations, deserialization and mapping, persistence, callbacks, authorization and presentation logic go. We have layers for that.
3. The common workflows for web applications are identified and implemented in Trailblazer.
4. Inheritance, composition and modules allow to share any kind of logic between use cases. This allows to reuse validations, rendering code or parts of your persistence for different user roles, different models, ...

you save time by using a higher level structure that works for many people


## Loose Coupling

Trailblazer decouples your business logic from the framework you use.

The components of Trailblazer are usable in any framework: Rails, Sinatra, Lotus, Roda, Grape or Webmachine - you name it.

This provides your applications with a cleaner architecture, which allows for easier framework updates, increased performance and simple, concise tests, which decreases overall development time.

## Faster, Easier to Debug, Understandable

Each layer in Trailblazer has a minimal scope and no access to global state. Debugging turns into quick tests against the problematic components. Where finding performance bottlenecks in Rails is difficult, in Trailblazer this is a matter of observing profilers, disabling suspicous components and fixing the leaks.

## Intuitive File Layout

A new file layout organizes files by domain, not by technology. Functions in your application now belong to standalone components that can easily be shared as gems and make navigation easier.

New developers will find their way into the project much faster than in a traditional Rails setup.

By structuring the application into concepts, less merge conflicts will happen, and duplication is almost ausgeschlossen as locations of logic are very clear.

## Modular: Pick What You Need

Trailblazer is a collection of very mature gems. Gems that have been around for many years and are in use in ten-thousands of production apps.

You pick what you need.

Rails, Lotus, Roda, Webmachine or Grape, they all work fine with Trailblazer's architecture.

The persistence layer is completely up to you, too. Use ActiveRecord, Lotus::Model, ROM, or Sequel. They will handle the persisting of data and retrieval. Keep them free of validations and callbacks, that is Trailblazer's job now.

### Cells

View models from the Cells gem are objects that embrace fragments of your UI. They can render arbitrary views, provide decoration for the presented objects, and are 120% faster than ActionView.

### Operation

An operation implements the Gang of Four `Command` pattern. It orchestrates all behavior between request dispatch and presentation, including persistence using the ORM of your choice.

Every operation keeps a form object to validate incoming data. This includes parameter whitelisting and supercedes strong_parameters.

The power of an operation lies in the encapsulation of a task, hiding performed work from the caller and making the task reusable.

### Reform

Form objects in Trailblazer and its operations are provided by the Reform gem which can deserialize and validate nested forms into object graphs and push the sane data to models.

Forms can also easily be rendered using form builders or your homegrown form renderer.

### Representable/Roar

To handle documents for APIs, the Representable gem gives you representers. They allow deserializing of incoming form data, JSON documents or XML. They also allow rendering documents from the same representer.

### Disposable

Modelling your persistent models into domain objects that focus on what you want to do, not how to store it, you use twins from the Disposable gem.



tests:
op: input => output

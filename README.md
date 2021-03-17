# goibus - golang implementation of libibus

This project was originally designed and developed by [sarim](https://github.com/sarim/goibus).

This fork aims to keep the project update with new Go versions, resolving pre-existing issues, adding new features.

For any developers who want to contribute, PRs are always welcome.

## Introduce

goibus implements the libibus bindings in golang.
goibus can be used to create IBus engines aka develop custom input methods.

IBus is an Intelligent Input Bus.
It provides full featured and user friendly input method user interface.
It also may help developers to develop input method easily.

This library is little bit different than other libibus bindings/wrappers.
Instead of wrapping `libibus c library` or `GOBject-Introspection`, it implements whole functionality by communicating over DBus IPC.
Because of that it is a independent 100% pure golang library without any native dependencies.

libibus has various classes that are not absolutely required for creating engines.
This library only implements engine related classes.
Some uncommon class/methods are also skipped for now.

## Implementation.

| libibus                                                                         | -                   | goibus                                                                              |
| ------------------------------------------------------------------------------- | ------------------- | ----------------------------------------------------------------------------------- |
| [IBusAttrList](http://ibus.github.io/docs/ibus-1.5/IBusAttrList.html)           | :ok:  | Implemented In `text.go`                                                            |
| [IBusAttribute](http://ibus.github.io/docs/ibus-1.5/IBusAttribute.html)         | :ok:  | Implemented In `text.go`                                                            |
| [IBusBus](http://ibus.github.io/docs/ibus-1.5/IBusBus.html)                     | :ok:  | Implemented In `bus.go`                                                             |
| [IBusComponent](http://ibus.github.io/docs/ibus-1.5/IBusComponent.html)         | :ok:  | Implemented In `component.go`                                                       |
| [IBusConfig](http://ibus.github.io/docs/ibus-1.5/IBusConfig.html)               | :red_circle:        | Ignored, not implemented                                                            |
| [IBusConfigService](http://ibus.github.io/docs/ibus-1.5/IBusConfigService.html) | :red_circle:        | Ignored, not implemented                                                            |
| [IBusEngine](http://ibus.github.io/docs/ibus-1.5/IBusEngine.html)               | :ok:  | Implemented In `engine.go`                                                          |
| [IBusEngineDesc](http://ibus.github.io/docs/ibus-1.5/IBusEngineDesc.html)       | :ok:  | Implemented In `engineDesc.go`                                                      |
| [IBusFactory](http://ibus.github.io/docs/ibus-1.5/IBusFactory.html)             | :ok:  | Implemented In `factory.go`                                                         |
| [IBusHotkeyProfile](http://ibus.github.io/docs/ibus-1.5/IBusHotkeyProfile.html) | :red_circle:        | Ignored, not implemented                                                            |
| [IBusInputContext](http://ibus.github.io/docs/ibus-1.5/IBusInputContext.html)   | :large_blue_circle: | Ignored, relevant inherited signals implemented in `Engine`                         |
| [IBusKeymap](http://ibus.github.io/docs/ibus-1.5/IBusKeymap.html)               | :large_blue_circle: | Ignored for now, will implement                                                     |
| [IBusLookupTable](http://ibus.github.io/docs/ibus-1.5/IBusLookupTable.html)     | :ok:  | Implemented In `lookupTable.go`                                                     |
| [IBusObject](http://ibus.github.io/docs/ibus-1.5/IBusObject.html)               | :ok:  | Ignored, Parent/Interface class, relevant inherited signals implemented in `Engine` |
| [IBusObservedPath](http://ibus.github.io/docs/ibus-1.5/IBusObservedPath.html)   | :red_circle:        | Ignored, not implemented                                                            |
| [IBusPanelService](http://ibus.github.io/docs/ibus-1.5/IBusPanelService.html)   | :red_circle:        | Ignored, not implemented                                                            |
| [IBusPropList](http://ibus.github.io/docs/ibus-1.5/IBusPropList.html)           | :ok:  | Implemented In `property.go`                                                        |
| [IBusProperty](http://ibus.github.io/docs/ibus-1.5/IBusProperty.html)           | :ok:  | Implemented In `property.go`                                                        |
| [IBusProxy](http://ibus.github.io/docs/ibus-1.5/IBusProxy.html)                 | :red_circle:        | Ignored, not implemented                                                            |
| [IBusRegistry](http://ibus.github.io/docs/ibus-1.5/IBusRegistry.html)           | :red_circle:        | Ignored, not implemented                                                            |
| [IBusSerializable](http://ibus.github.io/docs/ibus-1.5/IBusSerializable.html)   | :ok:  | Not needed in golang, All implemented classes are Serializable                      |
| [IBusService](http://ibus.github.io/docs/ibus-1.5/IBusService.html)             | :ok:  | Ignored, not needed. Parent/Interface class                                         |
| [IBusText](http://ibus.github.io/docs/ibus-1.5/IBusText.html)                   | :ok:  | Implemented In `text.go`                                                            |

## Install

```sh
go get github.com/haunt98/goibus
```

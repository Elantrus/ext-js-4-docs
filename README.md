# ExtJS 4 Documentation

Complete ExtJS 4 documentation in Markdown format, extracted from the official Sencha API.

## About

This is a comprehensive collection of ExtJS 4.2.1 documentation, organized in Markdown files for easy navigation and reference. The documentation includes all major framework classes, organized by namespace.

## Content

✅ **67 documented classes** including:
- Basic class information (extends, aliases, etc.)
- Main class description
- Code examples
- Configuration options (Config options)
- Properties
- Methods
- Events
- CSS Variables
- CSS Mixins

## Organization

The documentation is organized by namespace, following the ExtJS class structure:

```
📁 app/                    - Application framework classes
  📁 domain/              - Event domain classes
📁 button/                - Button components
📁 data/                  - Data management classes
📁 direct/                - Direct remoting classes
📁 layout/                - Layout management classes
  📁 container/           - Container layout classes
📁 panel/                 - Panel components
📁 util/                  - Utility classes
📄 *.md                   - Core framework classes
```

## Documentation Structure

Each class documentation follows this structure:

```markdown
# ClassName

**Extends:** ParentClass
**Widget Alias:** alias
**Alternate Names:** alternate names

## Description
Main class description...

## Examples
### Example 1
\`\`\`javascript
// Code example
\`\`\`

## Config options
### configName
**Type:** ConfigType
Configuration description...

## Properties
### propertyName
**Type:** PropertyType
Property description...

## Methods
### methodName
Method description...

## Events
### eventName
Event description...

## CSS Variables
### $css-variable
CSS variable description...

## CSS Mixins
### mixin-name
CSS mixin description...
```

## Popular ExtJS 4 Classes

Some of the most commonly used classes included in this documentation:

### Core Components
- `Ext.Component` - Base component class
- `Ext.panel.Panel` - Basic panel component
- `Ext.button.Button` - Button component
- `Ext.container.Container` - Container component

### Application Framework
- `Ext.app.Application` - Application class
- `Ext.app.Controller` - Controller class
- `Ext.app.EventDomain` - Event domain base class

### Data Management
- `Ext.data.AbstractStore` - Abstract store class

### Layout Management
- `Ext.layout.container.Accordion` - Accordion layout

### Utilities
- `Ext.Ajax` - AJAX utilities
- `Ext.Array` - Array utilities
- `Ext.Date` - Date utilities
- `Ext.Function` - Function utilities
- `Ext.JSON` - JSON utilities
- `Ext.Number` - Number utilities
- `Ext.Object` - Object utilities
- `Ext.String` - String utilities

### Core Framework
- `Ext.Base` - Base class for all Ext classes
- `Ext.Class` - Class system
- `Ext.ClassManager` - Class manager
- `Ext.Loader` - Dynamic class loader
- `Ext.Template` - Template class
- `Ext.XTemplate` - Advanced template class

## Usage

Simply browse the documentation files to find the class you need. Each file contains comprehensive information about the class, including configuration options, properties, methods, and events.

## Contributing

Feel free to contribute improvements:

1. Fork the project
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License

MIT License

## Source

This documentation was extracted from the official Sencha ExtJS 4.2.1 API documentation.

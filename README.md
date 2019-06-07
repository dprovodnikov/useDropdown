# useDropdown

## Intent

Dropdown behaviour is pretty common and is reimplemented over and over again any time you need a slightly different dropdown. What this package simply does is extract the most common behaviour into a small react hook, so you can only implement the appearance.

## Install

```bash
$ npm i use-dropdown
```

## Usage example

```javascript
import React from 'react';
import useDropdown from 'use-dropdown';

const Select = function () {
  const [containerRef, isOpen, open, close] = useDropdown();

  return (
    <div className="select-container" ref={containerRef}>
      <Input onFocus={open} />

      {isOpen && (
        <SelectOptions>
          <Option>First option</Option>
          <Option>Second option</Option>
          <Option>Third option</Option>
        </SelectOptions>
      )}

      <button onClick={close}>
        Close select
      </button>
    </div>
  );
};
```

The hook will observe clicks outside the container (this is what the `containerRef` is for) and close the dropdown when they happen.
The close-on-click-outside feature will not work if you don't set the `containerRef` to what you consider the container of your dropdown.

This is pretty much all you need to know to use this hook.

## Requirements
- React^16.8

## License
MIT
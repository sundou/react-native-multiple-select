# react-native-multiple-select

[![npm](https://img.shields.io/npm/v/react-native-multiple-select.svg)](https://www.npmjs.com/package/react-native-multiple-select) [![Downloads](https://img.shields.io/npm/dt/react-native-multiple-select.svg)](https://www.npmjs.com/package/react-native-multiple-select) [![Licence](https://img.shields.io/npm/l/react-native-multiple-select.svg)](https://www.npmjs.com/package/react-native-multiple-select)

> Simple multi-select component for react-native (Select2 for react-native).

![double animate search](https://user-images.githubusercontent.com/16062709/30780683-cfc1488e-a108-11e7-9429-ca92d680b078.gif)  ![double](https://user-images.githubusercontent.com/16062709/30780684-cfcb3eca-a108-11e7-877c-80620ab8b2bb.gif)  ![single](https://user-images.githubusercontent.com/16062709/30780685-cfd619f8-a108-11e7-88ee-9f337ac2c131.gif)



## Installation

``` bash
$ npm install react-native-multiple-select --save
```
or use yarn

``` bash
$ yarn add react-native-multiple-select
```


## Usage
Note: Ensure to add and configure [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons) to your project before using this package.

The snippet below shows how the component can be used


```javascript
// import component
import MultiSelect from 'react-native-multiple-select';

const items = [{
  id: '92iijs7yta',
  name: 'Ondo',
}, {
  id: 'a0s0a8ssbsd',
  name: 'C2G',
}, {
  id: '16hbajsabsd',
  name: 'Calabar',
}, {
  id: 'nahs75a5sg',
  name: 'Fourth Item',
}, {
  id: '667atsas',
  name: 'Fifth Item',
}];
 
let selectedItem = selectedItems => {
    // do something with selectedItems
    console.log(selectedItems);
};

<MultiSelect
  animate
  items={items}
  uniqueKey="id"
  selectedItemsChange={selectedItem}
  selectedItems={[]}
  selectText="Pick Items"
  searchInputPlaceholderText="Search Items..."
  altFontFamily="ProximaNova-Light"
  tagRemoveIconColor="#CCC"
  tagBorderColor="#CCC"
  tagTextColor="#CCC"
  selectedItemTextColor="#CCC"
  selectedItemIconColor="#CCC"
  itemTextColor="#000"
  searchInputStyle={{ color: '#CCC' }}
  submitButtonColor="#CCC"
  submitButtonText="Submit"
/>
    
```

The component takes 3 compulsory props - `items`, `uniqueKey` and `selectedItemsChange`. Other props are optional. The table below explains more.


## Props

| Prop        | Required   | Purpose  |
| ------------- |-------------| -----|
| items      | Yes | (Array) List of items to display in the multi-select component. JavaScript Array of objects. Each object must contain a name and unique identifier (Check sample above) |
| uniqueKey      | Yes      | (String) Unique identifier that is part of each item's properties. Used internally as means of identifying each item (Check sample below) |
| single | No     | (Boolean) Toggles select component between single option and multi option |
| animate | No     | (Boolean) Adds animation to select dropdown |
| selectedItemsChange | Yes      | (Function) JavaScript function passed in as an argument. The function is to be defined with an argument (selectedItems). Triggered when `Submit` button is clicked (for multi select) or item is clicked (for single select). (Check sample above) |
|selectedItems | No      | (Array) List of selected items. JavaScript Array of objects that is part of the items (check above), that cna be instantiated with the component |
| selectText | No     | (String) Text displayed in main component |
| searchInputPlaceholderText | No      | (String) Placeholder text displayed in multi-select filter input |
| fontFamily | No     | (String) Custom font family to be used in component (affects all text except `searchInputPlaceholderText` described above) |
| altFontFamily | No      | (String) Font family for `searchInputPlaceholderText` |
| tagRemoveIconColor | No      | (String) Color to be used for the remove icon in selected items list |
| tagBorderColor | No      | (String) Border color for each selected item  |
| tagTextColor | No  | (String) Text color for selected items list |
| selectedItemFontFamily | No   | (String) Font family for each selected item in multi-select drop-down |
| selectedItemTextColor | No   | (String) Text color for each selected item in multi-select drop-down |
| selectedItemIconColor | No     | (String) Color for `selected` check icon for each selected item in multi-select drop-down |
| itemFontFamily | No   | (String) Font family for each non-selected item in multi-select drop-down |
| itemTextColor | No   | (String) Text color for each non-selected item in multi-select drop-down |
| searchInputStyle | No   | (Object) Style object for multi-select input element  |
| submitButtonColor | No   | (String) Background color for submit button  |
| submitButtonText | No   | (String) Text displayed on submit button  |

## Note

- When using the `single` prop, `selectedItems` should still be passed in as an array of selected object. Also, when an item is selected in the single mode, the selected item is returned as an array of object.

- The `items` props must be passed as an array of objects with a compulsory `name` key present in each object as the name key is used to display the items in the options component.

### Removing all selected items

To use, add ref to MultiSelect component in parent component, then call method against reference. i.e.

```javascript
<MultiSelect
  ref={c => this._multiSelect = c}
  ...
/>

clearSelectedCategories = () => {
   this._multiSelect.removeAllItems();
};
    
``` 


## Contributing

Contributions are **welcome** and will be fully **credited**.

Contributions are accepted via Pull Requests on [Github](https://github.com/toystars/react-native-multiple-select).


### Pull Requests

- **Document any change in behaviour** - Make sure the `README.md` and any other relevant documentation are kept up-to-date.

- **Consider our release cycle** - We try to follow [SemVer v2.0.0](http://semver.org/). Randomly breaking public APIs is not an option.

- **Create feature branches** - Don't ask us to pull from your master branch.

- **One pull request per feature** - If you want to do more than one thing, send multiple pull requests.

- **Send coherent history** - Make sure each individual commit in your pull request is meaningful. If you had to make multiple intermediate commits while developing, please [squash them](http://www.git-scm.com/book/en/v2/Git-Tools-Rewriting-History#Changing-Multiple-Commit-Messages) before submitting.


## Issues

Check issues for current issues.

## Author

[Mustapha Babatunde](https://twitter.com/iAmToystars)
 

## License

The MIT License (MIT). Please see [LICENSE](LICENSE) for more information.
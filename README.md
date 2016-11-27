# backselect
select component based on [backbone](https://github.com/jashkenas/backbone)
## Introduction
It is a lightweight, small size and  powerful select component,which is more beautiful than browser select.when changed,it will trigger `changed` event,which arguments will include oldVal,newVal,isDefault.
## Feature
* single select,just like radio
* multiple select,just like checkbox
* customize yourself className to change list item stylesheet
* adaptable width and height
* AMD or CMD support
* ...

## Usage
It is based on backbone. So ,it is depend on [jquery](https://github.com/jquery/jquery),[underscore](https://github.com/jashkenas/underscore),[backbone](https://github.com/jashkenas/backbone).you must install those before using backselect.
if you have installed jquery,underscore,backbone,you can use it,like below
* install it  `npm install backselect`
* include `select.js` and `src/select.css` in your html.

## Example
you can just given options just like `new BackSelect(options)`.

options
* **el** ,just like `Backbone.View` options el ,which define parent element,always be `div`
* **collection** ,just like `Backbone.View` options collection,which must be a `Backbone.Collection` instance,and the model must include **name**,**value** attributes,also can include **className**.The **value** must be uniqued.The **className** will be added into the list item whether which is selected,which can define yourself stylesheet for list item. 
* **itemType** , define select type,must be `backbone_radio` or `backbone_check`.if it is `undefined` or `null`,it is be setted `backbone_radio`.
* **itemCount** ,define show item count in a row ,just used  when **itemType** is `backbone_check`.if it is `undefined` or `null`,backselect will compute to adaptable parent element's width.
* **default** ,define which item will be selected when initializing.
* **silent** ,if it is true,backselect instance will trigger **changed** event after having gived **default**
* **placeholder** ,just like input element's placeholder.
* **empty**, define whether show an empty item ,just used when **itemType** is `backbone_radio`.

single select
```
var options = {
            el: '#example_01',
            collection: collection,
            placeholder: '请选择级别',
            default: ['1'],
            silent: true,
            empty:true
        };
var roleSelect = new BackSelect(options);
var otherView = new Backbone.View();
otherView.listenTo(roleSelect, 'changed', changed);
```
multiple select
```
var options = {
            el: '#example_01',
            collection: collection,
            placeholder: '请选择级别',
            itemType:'backbone_check',
            default: ['1'],
            silent: true,
        };
var roleSelect = new BackSelect(options);
var otherView = new Backbone.View();
otherView.listenTo(roleSelect, 'changed', changed);
```

## Contributing
I welcome contributions of all kinds from anyone.
* [Bug reports](https://github.com/snayan/backselect/issues) 
* [Feature requests](https://github.com/snayan/backselect/issues)
* [Pull requests](https://github.com/snayan/backselect/pulls)

## License
Licensed under the MIT License

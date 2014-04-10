# UI5 Snippets for Atom

A package of snippets for [SAPUI5](sapui5.hana.ondemand.com/sdk/) and [OpenUI5](openui5.hana.ondemand.com)

(early days yet, I will be adding more, sourcing from my [SublimeUI5](https://github.com/qmacro/SublimeUI5) package)

![OpenUI5 Logo](http://sap.github.io/openui5/images/icotxt_white_220x72_blue_open.png)

Snippets begin `ui5`

## HTML

### index.m

`ui5indexm` - Index file for sap.m-based app.

```html
<!DOCTYPE HTML>
<html>
  <head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta charset="UTF-8">

    <title>${1:App Title}</title>

    <script id="sap-ui-bootstrap"
      type="text/javascript"
      src="/sapui5/latest/resources/sap-ui-core.js"
      data-sap-ui-theme="${2:sap_bluecrystal}"
      data-sap-ui-libs="${3:sap.m}"
      data-sap-ui-xx-bindingSyntax="${5:complex}"
    >
    </script>

    <script>

    $0

    </script>
  </head>

  <body class="sapUiBody" id="content" />
</html>
```

### index.m.spmvc

`ui5indexmspmvc` - Index file for single-page MVC sap.m-based app.

```html
<!DOCTYPE HTML>
<html>
  <head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta charset="UTF-8">

    <title>${1:App Title}</title>

    <script id="sap-ui-bootstrap"
      type="text/javascript"
      src="/sapui5/latest/resources/sap-ui-core.js"
      data-sap-ui-theme="${2:sap_bluecrystal}"
      data-sap-ui-libs="${3:sap.m}"
      data-sap-ui-xx-bindingSyntax="${5:complex}"
    >
    </script>

    <!-- XML-based view definition -->
    <script id="view1" type="sapui5/xmlview">
      <mvc:View
        controllerName="local.controller"
        xmlns:mvc="sap.ui.core.mvc"
        xmlns="sap.m">
          ${6:<!-- Add your XML-based controls here -->}
      </mvc:View>
    </script>

    <script>

      // Controller definition
      sap.ui.controller("local.controller", {

        $0

      });

      // Instantiate the View, assign a model
      // and display
      var oView = sap.ui.xmlview({
        viewContent: jQuery('#view1').html()
      });

      oView.setModel(new sap.ui.model.json.JSONModel({
          ${7:name: "value"}
      }));

      oView.placeAt('content');

    </script>

  </head>

  <body class="sapUiBody" id="content" />
</html>
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request!

## License

MIT © DJ Adams

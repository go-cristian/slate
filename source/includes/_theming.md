# Theming

> Set SDK colors:

```xml
<resources xmlns:tools="http://schemas.android.com/tools">
  <style name="AppTheme.Light" parent="Theme.AppCompat.Light.NoActionBar">
    ...
    <item name="pager_primary_color">@color/colorPrimary</item>
    <item name="pager_secondary_color">@color/pager_gray</item>
    <item name="pager_third_color">@color/pager_blue</item>
    <item name="pager_error_color">@color/pager_red</item>
    <item name="pager_warning_color">@color/pager_yellow</item>
    ...
  </style>
</resources>
```

For theming our views we provide custom xml attributes for exposing the main colors.
<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128640662/24.2.1%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E1562)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->

# WPF Bars - Create a container for BarItem links

This example creates a [BarLinkContainerItem](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarLinkContainerItem), which is a container for item links. The [BarLinkContainerItem](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarLinkContainerItem) contains `Cut`, `Copy` and `Paste` commands. 

## Implementation details

In the following code snippet, the [`BarManager`](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarManager) contains multiple [`BarButtonItem`](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarButtonItem) elements that represent individual commands: Cut, Copy, Paste, Undo, and Redo. To group the first three commands, the example uses a `BarLinkContainerItem`.

The `BarLinkContainerItem` acts as a container for item links:

```xaml
<dxb:BarLinkContainerItem x:Name="linkContainerItem1" Content="Edit Commands">
    <dxb:BarLinkContainerItem.ItemLinks>
        <dxb:BarButtonItemLink BarItemName="itemCut" />
        <dxb:BarButtonItemLink BarItemName="itemCopy" />
        <dxb:BarButtonItemLink BarItemName="itemPaste" />
    </dxb:BarLinkContainerItem.ItemLinks>
</dxb:BarLinkContainerItem>
```

The **Edit** submenu ([`BarSubItem`](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarSubItem)) includes a [`BarLinkContainerItemLink`](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarSubItemLink), which references the same group of commands and displays them as submenu items:

```xaml
<dxb:BarSubItem Content="Edit" x:Name="subMenu1">
    <dxb:BarSubItem.ItemLinks>
        <dxb:BarLinkContainerItemLink BarItemName="linkContainerItem1" />
    </dxb:BarSubItem.ItemLinks>
</dxb:BarSubItem>
```

A top-level bar (**Bar 1**) displays the container item and submenu along with `Undo` and `Redo` commands. Separators visually separate item groups:

```xaml
<dxb:BarManager.Bars>
    <dxb:Bar x:Name="bar1" Caption="Bar 1">
        <dxb:Bar.ItemLinks>
            <dxb:BarLinkContainerItemLink BarItemName="linkContainerItem1" />
            <!--Create a separator between links-->
            <dxb:BarItemLinkSeparator />
            <dxb:BarButtonItemLink BarItemName="itemUndo" />
            <dxb:BarButtonItemLink BarItemName="itemRedo" />
            <!--Create a separator between links-->
            <dxb:BarItemLinkSeparator />
            <dxb:BarSubItemLink BarItemName="subMenu1" />
        </dxb:Bar.ItemLinks>
    </dxb:Bar>
</dxb:BarManager.Bars>
```

This setup allows you to reuse a group of related commands in multiple containers, such as bars and submenus.

## Files to Review

* [Window1.xaml](./CS/BarLinkContainerItem/Window1.xaml) (VB: [Window1.xaml](./VB/BarLinkContainerItem/Window1.xaml))
* [Window1.xaml.cs](./CS/BarLinkContainerItem/Window1.xaml.cs) (VB: [Window1.xaml.vb](./VB/BarLinkContainerItem/Window1.xaml.vb))

## Documentation

- [BarContainerControl](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarContainerControl)
- [BarLinkContainerItem](https://docs.devexpress.com/WPF/DevExpress.Xpf.Bars.BarLinkContainerItem)
- [Bars](https://docs.devexpress.com/WPF/6194/controls-and-libraries/ribbon-bars-and-menu/bars?p=netframework)

## More Examples

- [WPF Bars - Use separators to group bar item links](https://github.com/DevExpress-Examples/wpf-bars-visually-separate-bar-items)
- [MVVM Application with WPF Bars](https://github.com/DevExpress-Examples/mvvm-application-with-wpf-bars)
- [WPF PDF Viewer - Customize the Integrated Bar's Commands](https://github.com/DevExpress-Examples/wpf-pdf-viewer-customize-bar-manager)
- [Chart for WPF - Create a 2D Side-by-Side Bar chart](https://github.com/DevExpress-Examples/wpf-charts-create-2d-side-by-side-bar-chart)
- [WPF MVVM Behaviors - Display Theme Selectors Based on BarItems and Hide Themes from List](https://github.com/DevExpress-Examples/wpf-mvvm-behaviors-barItems-based-theme-selectors)
- [WPF Dock Layout Manager - Merge Bars in Controls That Support Automatic Merging](https://github.com/DevExpress-Examples/wpf-docklayoutmanager-merge-bars-in-controls-that-support-automatic-merging)

<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=wpf-bars-create-baritem-link-container&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=wpf-bars-create-baritem-link-container&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->

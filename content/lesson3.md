# Building a Simple User Interface

In this lesson, you create a layout in XML that includes a text field and a button. In the next lesson, your app responds when the button is pressed by sending the content of the text field to another activity.

The graphical user interface for an Android app is built using a hierarchy of View and ViewGroup objects. View objects are usually UI widgets such as buttons or text fields. ViewGroup objects are invisible view containers that define how the child views are laid out, such as in a grid or a vertical list.

Android provides an XML vocabulary that corresponds to the subclasses of View and ViewGroup so you can define your UI in XML using a hierarchy of UI elements.

Layouts are subclasses of the ViewGroup. In this exercise, you'll work with a LinearLayout.

![ViewGroup](/images/viewgroup.png)

**Figure 1**. Illustration of how `ViewGroup` objects form branches in the layout and contain other `View` objects.
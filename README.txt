::Title and Purpose of Application::
C482 Software I Performance Assessment
This application is meant for use in managing the inventory of parts and products for a small manufacturing organization.
Parts can be tracked as In-House (with a machine ID) or Outsourced (with a company name), and products can be built from any number of associated parts.

::Author Information::
Author: Ashley Barone
Contact Info: abaro20@wgu.edu
Application Version: 1.0.0.0
Date: November 29, 2021

::Version Information::
IntelliJ IDEA 2021.3 (Community Edition)
Runtime version: 11.0.13+7-b1751.19 amd64
VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.
Windows 10 10.0
GC: G1 Young Generation, G1 Old Generation
Memory: 768M
Cores: 4

JDK version: JDK-17.0.1

JavaFX version: JavaFX-SDK-17.0.1

::Running the Program::
To run this program, first, open the folder in IntelliJ. Next, you have to update your IDE settings to the program.
To do this, you will access File>Project Structure to create a PATH_TO_FX leading to your JavaFX SDK library.
Then, you will access File>Settings to add your JavaFX SDK library.
Finally you will create a new Application configuration with the following format:
 - Select main.Main as your Main class.
 - Click Modify Options and enable VM Option. In that field, you will paste this:
     --module-path ${PATH_TO_FX} --add-modules javafx.fxml,javafx.controls,javafx.graphics
 - Next, you will ensure you have the correct JavaFX SDK selected in the top combo box.
 - Finally, you can name your configuration and click Apply then Okay.
The application loads with sample parts and products so that all features can be tested right away.

::Logical Error::
The associated parts table on the Modify Product screen was not populating with the selected product's associated parts until another part was added from the all parts table, causing a null pointer error in the Modify Product controller's initialize method.
I fixed this by initializing the selected product in the event handler that opens the Modify Product screen, before it is used in the Modify Product controller.

::Future Enhancement::
A future enhancement for this application would be the ability to connect to a database that could be synced between multiple devices.
This would allow for remote updates to the parts and products lists, and would provide cleaner data storage by implementing constraints and structure for each object created within the application.
Another enhancement would be the ability to search products by their associated parts from the main screen, allowing quicker access to product details without changing screens.

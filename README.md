# StackViewLibrary
The StackView Library is a powerful and flexible Android library that simplifies the implementation of expandable and collapsible stack views in your Android application. It provides a convenient abstraction layer with customizable features, making it easy to create engaging and interactive stack-based user interfaces.

## Features
* Create stack views with expandable and collapsible behavior.
* Support for multiple states and transitions within the stack.
* Customizable layout and appearance of stack items.
* Efficient management of view inflation, enabling smooth performance.
* Respond to view actions and changes through the provided interfaces.
* Easy integration with your existing Android application.
  
## Installation
To use the StackView Library in your Android project, follow these steps:
1. Add the following in your root build.gradle
   ```
   allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
   ```
2. Add the library as a dependency in your project's build.gradle file:
   ``` 
	dependencies {
	        implementation 'com.github.neelesh9924:StackViewLibrary:1.0.0'
	}
   ```
3. Sync your project to ensure the library is successfully added.

## Usage
To start using the StackView Library, follow these steps:
1. Add the StackViewLayout to your XML layout file:
  ```
  <?xml version="1.0" encoding="utf-8"?>
  <com.example.customViews.StackViewLayout xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:tools="http://schemas.android.com/tools"
      android:id="@+id/stackLayout"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:context=".MainActivity" />
  
  ```
2. Create an instance of StackFramework by providing the necessary parameters: the application context, a list of StackItem objects representing your view layouts, and the target layout where the stack views will be added.
  ```
  ArrayList<StackItem> stackItemsList = new ArrayList<>();
  stackItemsList.add(new StackItem(R.layout.pre_layout1, R.layout.main_layout1, R.layout.post_layout1, R.color.color1));
  stackItemsList.add(new StackItem(R.layout.pre_layout2, R.layout.main_layout2, R.layout.post_layout2, R.color.color2));
  stackItemsList.add(new StackItem(R.layout.pre_layout3, R.layout.main_layout3, R.layout.post_layout3, R.color.color3));
  stackItemsList.add(new StackItem(R.layout.pre_layout4, R.layout.main_layout4, R.layout.post_layout4, R.color.color4));
  
  stackFramework = new StackFramework(context, stackItemsList, stackLayout);
  ```
3. Retrieve the views added to the stack using the getViews() method and implement the ViewsAddedListener interface to handle the inflated views.
  ```
  stackFramework.getViews(new StackFramework.ViewsAddedListener() {
      @Override
      public void viewsAdded(ArrayList<CustomCardView> views) {
          // Handle the inflated views here
  
          View view1 = views.get(0);
          TextView textView = view1.findViewById(R.id.textView);
  
      }
  });
  ```
4. Set the completion state and enable the next view in the stack using the setCompleted() method. The setCompleted() method accepts three states:
   * INCOMPLETE: Marks the current view as incomplete.
   * COMPLETE: Marks the current view as complete.
   * COMPLETE_EXPAND_NEXT: Marks the current view as complete and expands the next view in the stack.

   Here's an example of how to use the setCompleted() method:
   ```
   stackFramework.setCompleted(view1, StackFramework.CompletionState.COMPLETE);
   ```
## Contributions
Contributions to the StackView Library are welcome! If you encounter any issues, have suggestions, or would like to contribute enhancements, please submit a pull request or open an issue in the GitHub repository.
  
## Credits
The StackView Library is developed and maintained by Neelesh Singh.



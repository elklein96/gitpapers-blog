***

Before you build your first Android App, you have to set up a development environment.

Eclipse is an **IDE** (Integrated Developer Evnironment). This means that it will help you out by correcting, organizing and compiling code.

***

## Downloading Eclipse


[Click here to download Eclipse](http://eclipse.org/downloads/packages/eclipse-standard-432/keplersr2)

The latest package of Eclipse (4.3.2) includes tools for Java development, and support for Git, a version control system.

When the file finished downloading, run through the installation wizard.

***

## Configuring Eclipse


Once you've opened up Eclipse, push *OK* when prompted to create a *workspace*. This will be the subdirectory where you store all of the projects on your computer.

Next, you need to install the Android SDK.

***

## Setting up the Android SDK and ADT Plugin

1. [Click here to download the Android SDK](http://developer.android.com/sdk/index.html).  Unpack it into a directory of your choice.

2. In Eclipse, select **Help -> Install New Software**.

3. Click *Add*.

4. In **Name** enter "ADT Plugin".  In **Location** enter `https://dl-ssl.google.com/android/eclipse/`. Click *OK*.

5. Select **Developer Tools** (leave NDK alone for now) then click *Next*.

6. Accept all of the agreements then click *Finish*.

7. Restart Eclipse.

8. In the "Welcome to Android Development" window select **Use existing SDKs**. Browse and select the directory where you unpacked the SDK.

9. In Eclipse, select **Window -> Android SDK Manager**.

10. Check **Tools**, **Extras** and all of the Android APIs you want to work with. Click **Install** and accept the license agreements.

***

Now that you've set up Eclipse it's time to make your first Android App!

***

## Hello, Android!

* In Eclipse, select **File -> New -> Android Application Project**.

* In **Application Name** enter "Hello Android". Click *Next* four times, the click *Finish*.

> Make sure you have MainActivity.java and activity_main.xml open; these are the Main Activity and Main Layout files.
> The Java code (in which Android apps are written) will go in the ".java" file, while all of the layout information will go in the ".xml" file.

* In the `MainActivity.java` file, you'll notice that a lot of auto-generated code is already there. We'll be focusing on the `onCreate` function. 

> When an Android app is launched, the first function to "fire off" is `onCreate`. 

After the line `setContentView(R.layout.activity_main);` insert the following: (There will be errors, just ignore for now)

	Button helloButton = (Button) findViewById(R.id.helloButton);

	helloButton.setOnClickListener(new OnClickListener (){
		@Override
		public void onClick(View view){
			
		}
	});

* In Eclipse, select **Source -> Organize Imports**.

* Next, go to `activity_main.xml`. Select `activity_main.xml` on the bottom of the page. After the line `setContentView(R.layout.activity_main);` insert the following:
	
	
	<Button
        android:id="@+id/helloButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button" />
    

* What did we just do? First, we created a Button, linked it to the button in `activity_main.xml` (the layout file) and assigned it a listener in `onCreate` (the Main Activity).  This means that 
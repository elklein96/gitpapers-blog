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

* In **Application Name** enter "Hello Android". Click *Next* four times, then click *Finish*.

> Make sure you have `MainActivity.java` and `activity_main.xml` open; these are the Main Activity and Main Layout files.
> The Java code (in which Android apps are written) will go in the `.java` file, while all of the layout information will go in the `.xml` file.

* We'll start with the layout. In the `activity_main.xml` select `activity_main.xml` on the bottom of the page to go the to XML view.

Insert the following code, replacing what is already in the XML file with:
	

	<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    xmlns:tools="http://schemas.android.com/tools"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:paddingBottom="@dimen/activity_vertical_margin"
	    android:paddingLeft="@dimen/activity_horizontal_margin"
	    android:paddingRight="@dimen/activity_horizontal_margin"
	    android:paddingTop="@dimen/activity_vertical_margin"
	    tools:context=".MainActivity" >

	    <Button
	        android:id="@+id/helloButton"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_alignParentBottom="true"
	        android:layout_centerHorizontal="true"
	        android:layout_marginBottom="150dp"
	        android:text="Click me!" />

	    <TextView
	        android:id="@+id/helloLabel"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_above="@+id/helloButton"
	        android:layout_centerHorizontal="true"
	        android:layout_marginBottom="48dp" />

	</RelativeLayout>
    

> We just created a button called "helloButton" and a TextView called "helloLabel". Both will be drawn when the app is started.

In the `MainActivity.java` file, you'll notice that a lot of auto-generated code is already there. We'll be focusing on the `onCreate` function. 

> When an Android app is launched, the first function to "fire off" is `onCreate`. 

When you find the `onCreate` method, replace it with this:

	@Override
	protected void onCreate(Bundle savedInstanceState) {
	    super.onCreate(savedInstanceState);
	    setContentView(R.layout.activity_main);

	    Button helloButton = (Button) findViewById(R.id.helloButton);
	    final TextView label = (TextView) findViewById(R.id.helloLabel);
	    
	    helloButton.setOnClickListener(new OnClickListener (){
			@Override
			public void onClick(View view){

			}
		});
	}

* In Eclipse, select **Source -> Organize Imports**.
    
* What did we just do? 

	1. We created a Button and a TextView.
	2. We linked the button in the layout file to a button in the `onCreate` method, and we named it `helloButton`.
	3. We linked the TextView in the layout file to a TextView in the `onCreate` method, and we named it `label`.
	4. We assigned the button a listener in `onCreate` (the Main Activity).

* Next, we need to tell the program what to do when the button is clicked.

After the line `public void onClick(View view){` insert the following:

	label.setText("Hello, Android!");

* Now when we click the button, the TextView, called `label`, will display "Hello, Android!"

***

## Testing the App

Now we have a few options to test our app:

1. We can create an Android Virtual Device to run our code.

2. We can run our app on a real phone.

We'll start with option 1.

***

## Creating an Android Virtual Device (AVD)

* In Eclipse, select **Window -> Android Virtual Device Manager**.

* In the AVDM window click *New*.

* In **AVD Name** enter "Nexus_4".

* In **Device** select "Nexus_4".

* In **Target** select "Android 4.4.2 - API Level 19".

* In **CPU/ABI** select "Intel Atom (x86)". (If it doesn't show up, skip this step)

* In **Emulation Options** check "Use Host GPU".

* Click *OK*.

* In the AVDM Window click on "Nexus_4" and hit *Start*. After the AVD starts up go to Eclipse and push the play (Run) button.

***

## Running the App on an Android Device

* On your Android Device go to **Settings -> More -> Developer Options** and turn it on.

> If Developer Options is not there, Google how to activate it on your version of Android.

* In **Developer Options** select *USB Debugging*.

* Plug the device into your computer, go to Eclipse and push the play (Run) button.
# How to get SIM number and IMEI number in Android?

### Step 1:
First, in the manifest file have to add a permission which is "READ_PHONE_STATE". This will enable to get Telephony manager where we can find the mobile number and so on.

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.bs23.aliahmed.simnumber">
    <uses-permission android:name="android.permission.READ_PHONE_STATE"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

### Step 2: 

#### Mobile number:
There is a class which is TelephonyManager where there is a function which is getLine1Number(); this function will fetch the device sim number and store it in a String variable, Like this:

`//Mobile Number
String telNumber = tm.getLine1Number();
if (telNumber != null)
   Toast.makeText(this, "Phone number: " + telNumber, Toast.LENGTH_LONG).show();
`

#### IMEI number:
In the TelephonyManager class, there is another method getDeviceId() which is responsible for IMEI number. Example :

`//Imei number
String IMEI = tm.getDeviceId();
if (IMEI != null) Toast.makeText(this, "IMEI number: " + IMEI, Toast.LENGTH_LONG).show();`

This way we can fetch SIM number and IMEI number in Android. 
Thank you and Happy coding.


 

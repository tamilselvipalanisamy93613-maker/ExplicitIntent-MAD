# Ex.No:3 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:


Start Android Studio and create a new project.
Design the first screen using XML with a Text Field and Explicit Intent Button.
Create a second Activity named SecondActivity.
Design the second screen using XML.
Create an Intent object in MainActivity.java.
Set the target Activity as SecondActivity.
Use startActivity() to open the second Activity when the button is clicked.
Display the message "This is Second Activity" on the second screen.
Run the application and verify the output.


## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: TAMILSELVI P
Registeration Number :212225040460
*/
```
## activity_main.xml
```
package com.example.explicitintent;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button explicitButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        explicitButton = findViewById(R.id.explicitButton);

        explicitButton.setOnClickListener(v -> {

            Intent intent = new Intent(MainActivity.this, SecondActivity.class);

            startActivity(intent);

        });
    }


}

```
## activity_second.xml
```
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">


    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This is Second Activity"
        android:textSize="25sp"
        android:textStyle="bold"/>


</LinearLayout>

```
## MainActivity.java
```
package com.example.explicitintent;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button explicitButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        explicitButton = findViewById(R.id.explicitButton);

        explicitButton.setOnClickListener(v -> {

            Intent intent = new Intent(MainActivity.this, SecondActivity.class);

            startActivity(intent);

        });
    }


}

```

## SecondActivity.java
```
package com.example.explicitintent;

import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);
    }


}

```

## OUTPUT

<img width="1917" height="1078" alt="Screenshot 2026-11-01 183615" src="https://github.com/user-attachments/assets/6a438c7b-3be3-4070-9606-9128d5b7ef4a" />

<img width="1917" height="1078" alt="Screenshot 2026-11-01 183626" src="https://github.com/user-attachments/assets/990a9ad3-9bad-48cb-802f-1b7a18199638" />

<img width="1917" height="1078" alt="Screenshot 2026-11-01 183531" src="https://github.com/user-attachments/assets/1a3d0b3c-f1e3-4afc-b9f6-655be5360a33" />


<img width="1917" height="1078" alt="Screenshot 2026-11-01 183659" src="https://github.com/user-attachments/assets/8dad39df-2419-44b1-a4c0-f8b5a52a87c1" />



## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



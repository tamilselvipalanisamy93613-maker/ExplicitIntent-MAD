# Ex.No:2(b) To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


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
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number" />

    <Button
        android:id="@+id/factorialButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial" />

</LinearLayout>
```
## activity_second.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24sp"
        android:textStyle="bold" />

</LinearLayout>

```
## MainActivity.java
```
package com.example.factorialintent;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText number;
    Button factorialButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        number = findViewById(R.id.number);
        factorialButton = findViewById(R.id.factorialButton);

        factorialButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String input = number.getText().toString();

                if (input.isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Enter a number", Toast.LENGTH_SHORT).show();
                    return;
                }

                int n = Integer.parseInt(input);

                if (n < 0 || n > 20) {
                    Toast.makeText(MainActivity.this,
                            "Enter a number between 0 and 20",
                            Toast.LENGTH_SHORT).show();
                    return;
                }

                long fact = 1;

                for (int i = 1; i <= n; i++) {
                    fact = fact * i;
                }

                Intent intent = new Intent(
                        MainActivity.this, SecondActivity.class);

                intent.putExtra("result",
                        "Factorial of " + n + " is " + fact);

                startActivity(intent);
            }
        });
    }
}
```

## SecondActivity.java
```
package com.example.factorialintent;

import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {

    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        result = findViewById(R.id.result);

        String value = getIntent().getStringExtra("result");

        result.setText(value);
    }
}
```

## OUTPUT

<img width="1916" height="1020" alt="Screenshot 2026-11-05 210006" src="https://github.com/user-attachments/assets/7f273611-152e-47c0-abc3-a43662f8939b" />


<img width="1917" height="1016" alt="Screenshot 2026-11-05 210043" src="https://github.com/user-attachments/assets/794d5e39-e7c7-4d8d-add1-bd3ab192f436" />


## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



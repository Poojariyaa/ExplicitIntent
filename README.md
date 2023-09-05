# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.
## AIM:
To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.

## EQUIPMENTS REQUIRED:
Latest Version Android Studio

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
~~~
/*
Program to print the text “ExplicitIntent”.
Developed by: POOJA V
Registeration Number : 212221040122
*/
~~~
## Activity_xml File:
~~~
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<EditText
    android:id="@+id/numberEditText1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginTop="172dp"
    android:ems="10"
    android:inputType="textPersonName"
    android:text=""
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.497"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />

<Button
    android:id="@+id/factorialButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginTop="340dp"
    android:text="Button"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.498"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
~~~
## Activity_xml 2 File:
~~~
 <?xml version="1.0" encoding="utf-8"?>
 <androidx.constraintlayout.widget.ConstraintLayout        xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".FactorialActivity">

<TextView
   android:id="@+id/factorialTextView"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:layout_marginTop="283dp"
   android:text="TextView"
   android:textSize="36dp"
   app:layout_constraintEnd_toEndOf="parent"
   app:layout_constraintStart_toStartOf="parent"
   app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
~~~
## MainActivity.java File:
~~~
  package com.example.factorialexplicit;

  import static com.example.factorialexplicit.R.id.factorialButton;
  import static com.example.factorialexplicit.R.id.numberEditText1;

  import androidx.appcompat.app.AppCompatActivity;

  import android.annotation.SuppressLint;
  import android.content.Intent;
  import android.os.Bundle;
  import android.view.View;
  import android.widget.Button;
  import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
private EditText numberEditText;
private Button factorialButton;

@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

numberEditText = findViewById(R.id.numberEditText1);
factorialButton = findViewById(R.id.factorialButton);

factorialButton.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        int number = Integer.parseInt(numberEditText.getText().toString());

        Intent intent = new Intent(MainActivity.this, FactorialActivity.class);
        intent.putExtra("number", number);
        startActivity(intent);
    }
});
}
}
~~~
## MainActivity.java 2 File:
~~~
package com.example.factorialexplicit;

import static com.example.factorialexplicit.R.id.factorialTextView;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

public class FactorialActivity extends AppCompatActivity {
private TextView factorialTextView;

@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_factorial);

factorialTextView = findViewById(R.id.factorialTextView);

Intent intent = getIntent();
int number = intent.getIntExtra("number", 0);

long factorial = calculateFactorial(number);
factorialTextView.setText("Factorial of " + number + " is " + factorial);
}

private long calculateFactorial(int number) {
  long factorial = 1;
  for (int i = 1; i <= number; i++) {
    factorial *= i;
}
return factorial;
}
}
~~~
## OUTPUT
![image](https://github.com/Poojariyaa/ExplicitIntent/assets/127511817/b49328c6-5f68-430a-ab5f-3832bfd4944d)


![image](https://github.com/Poojariyaa/ExplicitIntent/assets/127511817/2a99981d-ae2f-412e-a8aa-29ef718a116c)

![image](https://github.com/Poojariyaa/ExplicitIntent/assets/127511817/2af09f50-71ae-4f86-bc4b-f176b05853da)

## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

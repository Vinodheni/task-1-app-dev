# task-1-app-dev

Main_Activity.java

package com.myname.myapplication;

import android.app.Activity;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends Activity {

    private Button _increase;
    private TextView _value;
    private static int _counter = 0;
    private String _stringVal;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        _increase = (Button) findViewById(R.id.button);
        _value = (TextView) findViewById(R.id.textView1);


        _increase.setOnClickListener(new OnClickListener() {

            @Override
            public void onClick(View v) {

                Log.d("src", "Increasing value...");
                _counter++;
                _stringVal = Integer.toString(_counter);
                _value.setText(_stringVal);
            }
        });

    }
}
activity_main.xml      

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:gravity="center" >

    <RelativeLayout
        android:layout_width="fill_parent"
        android:layout_height="44dp"
        android:gravity="center_horizontal" >



        <TextView android:id="@+id/textView1"
            android:layout_width="50dp"
            android:layout_height="fill_parent"
            android:layout_alignBottom="@+id/button1"
            android:layout_toRightOf="@+id/button1"
            android:gravity="center"
            android:text="0" />

        <Button android:id="@+id/button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentTop="true"
            android:layout_toRightOf="@+id/textView1"
            android:text="&gt;" />

    </RelativeLayout>

</RelativeLayout>

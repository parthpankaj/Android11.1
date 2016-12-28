# Android11.1
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_margin="16dp"
    android:gravity="center_horizontal"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Android Blinking Animation"
        android:textSize="22sp" />

    <Button
        android:id="@+id/blinking_animation"
        android:layout_width="fill_parent"
        android:layout_height="100dp"
        android:layout_marginTop="16dp"
        android:text="Blinking Animation" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:onClick="startBlinkingAnimation"
        android:text="Start Blinking Animation" />

</LinearLayout>
--------------
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">

    <alpha
        android:duration="400"
        android:fromAlpha="0.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:repeatCount="infinite"
        android:repeatMode="reverse"
        android:toAlpha="1.0" />

</set>
--------
package com.example.pankaj.animation111;

import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;

public class AndroidBlinkAnimationExample extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void startBlinkingAnimation(View view) {
        Button button = (Button) findViewById(R.id.blinking_animation);
        Animation startAnimation = AnimationUtils.loadAnimation(getApplicationContext(),R.layout.blinking);
        button.startAnimation(startAnimation);
    }
}
------

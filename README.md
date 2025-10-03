<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FFF8DC"
    android:padding="16dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Dobierz kolor suwakami:" 
        android:textSize="16sp"
        android:layout_marginBottom="16dp"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center_vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="R"
            android:layout_marginEnd="8dp"/>

        <SeekBar
            android:id="@+id/seekR"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:max="255"/>

        <TextView
            android:id="@+id/valueR"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="0"
            android:layout_marginStart="8dp"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center_vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="G"
            android:layout_marginEnd="8dp"/>

        <SeekBar
            android:id="@+id/seekG"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:max="255"/>

        <TextView
            android:id="@+id/valueG"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="0"
            android:layout_marginStart="8dp"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center_vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="B"
            android:layout_marginEnd="8dp"/>

        <SeekBar
            android:id="@+id/seekB"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:max="255"/>

        <TextView
            android:id="@+id/valueB"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="0"
            android:layout_marginStart="8dp"/>
    </LinearLayout>

    <View
        android:id="@+id/colorPicked"
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:background="#000000"
        android:layout_marginTop="24dp"/>

    <TextView
        android:id="@+id/textColorRGB"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="0, 0, 0"
        android:layout_marginTop="8dp"/>
</LinearLayout>

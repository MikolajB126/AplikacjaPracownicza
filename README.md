<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FFF8DC"
    android:padding="16dp">

    <View
        android:id="@+id/colorPreview"
        android:layout_width="match_parent"
        android:layout_height="120dp"
        android:background="#FFFFFF" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Dobierz kolor suwakami i zapisz przyciskiem:"
        android:textSize="16sp"
        android:layout_marginTop="16dp"/>

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
            android:max="255"
            android:progress="255"/>

        <TextView
            android:id="@+id/valueR"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="255"
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
            android:max="255"
            android:progress="255"/>

        <TextView
            android:id="@+id/valueG"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="255"
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
            android:max="255"
            android:progress="255"/>

        <TextView
            android:id="@+id/valueB"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="255"
            android:layout_marginStart="8dp"/>
    </LinearLayout>

    <Button
        android:id="@+id/buttonPick"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Pobierz"
        android:background="#CD853F"
        android:textColor="#FFFFFF"
        android:layout_marginTop="16dp"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="60dp"
        android:orientation="horizontal"
        android:layout_marginTop="16dp"
        android:gravity="center_vertical">

        <View
            android:id="@+id/colorPicked"
            android:layout_width="60dp"
            android:layout_height="match_parent"
            android:background="#FFFFFF"/>

        <TextView
            android:id="@+id/textColorRGB"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="255, 255, 255"
            android:layout_marginStart="16dp"/>
    </LinearLayout>
</LinearLayout>

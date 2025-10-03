package com.example.koloryrgb;

import androidx.appcompat.app.AppCompatActivity;
import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.SeekBar;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    SeekBar seekR, seekG, seekB;
    TextView valueR, valueG, valueB, textColorRGB;
    View colorPreview, colorPicked;
    Button buttonPick;
    int r = 255, g = 255, b = 255;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        seekR = findViewById(R.id.seekR);
        seekG = findViewById(R.id.seekG);
        seekB = findViewById(R.id.seekB);
        valueR = findViewById(R.id.valueR);
        valueG = findViewById(R.id.valueG);
        valueB = findViewById(R.id.valueB);
        textColorRGB = findViewById(R.id.textColorRGB);
        colorPreview = findViewById(R.id.colorPreview);
        colorPicked = findViewById(R.id.colorPicked);
        buttonPick = findViewById(R.id.buttonPick);

        SeekBar.OnSeekBarChangeListener listener = new SeekBar.OnSeekBarChangeListener() {
            @Override
            public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
                if (seekBar == seekR) {
                    r = progress;
                    valueR.setText(String.valueOf(progress));
                } else if (seekBar == seekG) {
                    g = progress;
                    valueG.setText(String.valueOf(progress));
                } else if (seekBar == seekB) {
                    b = progress;
                    valueB.setText(String.valueOf(progress));
                }
                colorPreview.setBackgroundColor(Color.rgb(r, g, b));
            }

            @Override
            public void onStartTrackingTouch(SeekBar seekBar) {}

            @Override
            public void onStopTrackingTouch(SeekBar seekBar) {}
        };

        seekR.setOnSeekBarChangeListener(listener);
        seekG.setOnSeekBarChangeListener(listener);
        seekB.setOnSeekBarChangeListener(listener);

        buttonPick.setOnClickListener(v -> {
            colorPicked.setBackgroundColor(Color.rgb(r, g, b));
            textColorRGB.setText(r + ", " + g + ", " + b);
        });
    }
}

package com.example.colorpicker;

import android.graphics.Color;
import android.os.Bundle;
import android.widget.SeekBar;
import android.widget.TextView;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private SeekBar seekR, seekG, seekB;
    private TextView valueR, valueG, valueB, textColorRGB;
    private View colorPicked;

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

        colorPicked = findViewById(R.id.colorPicked);
        Button buttonPick = findViewById(R.id.buttonPick);

        SeekBar.OnSeekBarChangeListener colorChangeListener = new SeekBar.OnSeekBarChangeListener() {
            @Override
            public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
                updateColor();
            }

            @Override
            public void onStartTrackingTouch(SeekBar seekBar) { }

            @Override
            public void onStopTrackingTouch(SeekBar seekBar) { }
        };

        seekR.setOnSeekBarChangeListener(colorChangeListener);
        seekG.setOnSeekBarChangeListener(colorChangeListener);
        seekB.setOnSeekBarChangeListener(colorChangeListener);

        buttonPick.setOnClickListener(v -> {});

        updateColor();
    }

    private void updateColor() {
        int r = seekR.getProgress();
        int g = seekG.getProgress();
        int b = seekB.getProgress();

        colorPicked.setBackgroundColor(Color.rgb(r, g, b));
        textColorRGB.setText(r + ", " + g + ", " + b);

        valueR.setText(String.valueOf(r));
        valueG.setText(String.valueOf(g));
        valueB.setText(String.valueOf(b));
    }
}

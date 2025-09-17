package com.example.kalkulatorv2;

public enum Operation {
    ADD,
    SUBTRACT,
    MULTIPLY,
    DIVIDE,
    NONE
}

package com.example.kalkulatorv2;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    TextView screen;
    String currentInput = "";
    double firstNumber = 0;
    Operation currentOperation = Operation.NONE;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        screen = findViewById(R.id.screen);

        int[] numberButtonIds = {
                R.id.button0, R.id.button1, R.id.button2, R.id.button3,
                R.id.button4, R.id.button5, R.id.button6, R.id.button7,
                R.id.button8, R.id.button9, R.id.buttonDot
        };

        for (int id : numberButtonIds) {
            Button btn = findViewById(id);
            btn.setOnClickListener(this::onNumberClick);
        }

        int[] operationButtonIds = {
                R.id.buttonAdd, R.id.buttonSub, R.id.buttonMul, R.id.buttonDiv
        };

        for (int id : operationButtonIds) {
            Button btn = findViewById(id);
            btn.setOnClickListener(this::onOperationClick);
        }

        findViewById(R.id.buttonEquals).setOnClickListener(v -> calculate());
        findViewById(R.id.buttonCE).setOnClickListener(v -> {
            currentInput = "";
            firstNumber = 0;
            currentOperation = Operation.NONE;
            screen.setText("");
        });
        findViewById(R.id.buttonC).setOnClickListener(v -> {
            if (!currentInput.isEmpty()) {
                currentInput = currentInput.substring(0, currentInput.length() - 1);
                screen.setText(currentInput);
            }
        });
    }

    private void onNumberClick(View v) {
        Button btn = (Button) v;
        currentInput += btn.getText().toString();
        screen.setText(currentInput);
    }

    private void onOperationClick(View v) {
        if (!currentInput.isEmpty()) {
            firstNumber = Double.parseDouble(currentInput);
            currentInput = "";
            switch (v.getId()) {
                case R.id.buttonAdd: currentOperation = Operation.ADD; break;
                case R.id.buttonSub: currentOperation = Operation.SUBTRACT; break;
                case R.id.buttonMul: currentOperation = Operation.MULTIPLY; break;
                case R.id.buttonDiv: currentOperation = Operation.DIVIDE; break;
            }
            screen.setText("");
        }
    }

    private void calculate() {
        if (currentInput.isEmpty() || currentOperation == Operation.NONE) return;
        double secondNumber = Double.parseDouble(currentInput);
        double result = 0;
        switch (currentOperation) {
            case ADD: result = firstNumber + secondNumber; break;
            case SUBTRACT: result = firstNumber - secondNumber; break;
            case MULTIPLY: result = firstNumber * secondNumber; break;
            case DIVIDE:
                if (secondNumber == 0) { screen.setText("Error"); return; }
                result = firstNumber / secondNumber; break;
        }
        currentInput = String.valueOf(result);
        screen.setText(currentInput);
        currentOperation = Operation.NONE;
    }
}

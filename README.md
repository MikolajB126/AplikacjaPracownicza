<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#6DE3F2"
    android:orientation="vertical"
    android:padding="8dp">

    <TextView
        android:id="@+id/screen"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:background="#6DE3F2"
        android:gravity="end|bottom"
        android:padding="16dp"
        android:textSize="32sp"
        android:textColor="#000" />

    <GridLayout
        android:id="@+id/buttonGrid"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:columnCount="4"
        android:rowCount="4"
        android:layout_marginTop="16dp">

        <Button android:text="1" style="@style/CalcButton"/>
        <Button android:text="2" style="@style/CalcButton"/>
        <Button android:text="3" style="@style/CalcButton"/>
        <Button android:text="CE" style="@style/CalcButton"/>

        <Button android:text="4" style="@style/CalcButton"/>
        <Button android:text="5" style="@style/CalcButton"/>
        <Button android:text="6" style="@style/CalcButton"/>
        <Button android:text="C" style="@style/CalcButton"/>

        <Button android:text="7" style="@style/CalcButton"/>
        <Button android:text="8" style="@style/CalcButton"/>
        <Button android:text="9" style="@style/CalcButton"/>
        <Button android:text="+" style="@style/CalcButton"/>

        <Button android:text="." style="@style/CalcButton"/>
        <Button android:text="0" style="@style/CalcButton"/>
        <Button android:text="=" style="@style/CalcButton"/>
        <Button android:text="-" style="@style/CalcButton"/>

    </GridLayout>
</LinearLayout>
        for (int i = 0; i < grid.getChildCount(); i++) {
            View child = grid.getChildAt(i);
            if (child instanceof Button) {
                child.setOnClickListener(this::onButtonClick);
            }
        }
    }

    private void onButtonClick(View v) {
        Button btn = (Button) v;
        String text = btn.getText().toString();

        switch (text) {
            case "C":
                if (!currentInput.isEmpty()) {
                    currentInput = currentInput.substring(0, currentInput.length() - 1);
                    screen.setText(currentInput);
                }
                break;
            case "CE":
                currentInput = "";
                firstNumber = 0;
                currentOperation = Operation.NONE;
                screen.setText("");
                break;
            case "+":
                setOperation(Operation.ADD);
                break;
            case "-":
                setOperation(Operation.SUBTRACT);
                break;
            case "*":
                setOperation(Operation.MULTIPLY);
                break;
            case "/":
                setOperation(Operation.DIVIDE);
                break;
            case "=":
                calculate();
                break;
            default:
                currentInput += text;
                screen.setText(currentInput);
        }
    }

    private void setOperation(Operation op) {
        if (!currentInput.isEmpty()) {
            firstNumber = Double.parseDouble(currentInput);
            currentOperation = op;
            currentInput = "";
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

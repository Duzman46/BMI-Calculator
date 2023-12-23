# BMI Calculator

This is a simple BMI (Body Mass Index) calculator created using Python and the Tkinter library.

## How It Works

The BMI calculator takes user input for weight and height and calculates the BMI value. Based on the calculated BMI value, it categorizes the user's weight status as underweight, normal weight, overweight, obese, severely obese, or extremely obese.

## Requirements

This project requires Python and the Tkinter library. If you don't have Python installed, you can download it from the [official Python website](https://www.python.org/).

## Installation and Usage

1. Copy the code into a file and save it with a `.py` extension (for example, `bmi_calculator.py`).
2. Run the saved file to start the BMI calculator.

## Contribution

This project is still in development. If you'd like to contribute:

1. Fork the repository.
2. Add new features or fix bugs.
3. Submit a pull request to the main repository.

## License

This project is licensed under the MIT License. For more information, see the [LICENSE](LICENSE) file.

## Contact

For feedback or questions regarding the project, you can reach out via email at [furkanduzman46@gmail.com](mailto:furkanduzman46@gmail.com).


```python
import tkinter

window = tkinter.Tk()
window.config(padx=50,pady=30)
window.title("BMI Calculator")

def BMI_Calculate():
    user_weight = entry_weight.get()
    user_height = entry_height.get()
    if user_weight == '' or user_height == '':
        all_messages = "Enter both weight and height!"
    else:
        try:
            user_weight = float(entry_weight.get())
            user_height = float(entry_height.get())
            BMI_result = (user_weight)/((user_height/100)**2)
            if BMI_result<=18.5:
                category = "underweight"
            elif BMI_result<=24.9:
                category = "normal"
            elif BMI_result<=29.9:
                category = "overweight"
            elif BMI_result<=34.9:
                category = "obese"
            elif BMI_result<=34.9:
                category = "severely obese"
            else:
                category= "mordibly obese"
            all_messages = f"Your BMI is {BMI_result:.2f}. You are {category}"
        except ValueError:
            all_messages = "Enter a valid number!"
    
    end_message.config(text= all_messages)
message1 = tkinter.Label(text="Enter Your Weight(kg)")
message1.pack()

entry_weight = tkinter.Entry(width=10)
entry_weight.pack()

message2 = tkinter.Label(text="Enter Your Height(cm)")
message2.pack()

entry_height = tkinter.Entry(width=10)
entry_height.pack()

calculate_button = tkinter.Button(text="Calculate",command=BMI_Calculate)
calculate_button.pack(padx=10,pady=10)

end_message = tkinter.Label()
end_message.pack()


window.mainloop()

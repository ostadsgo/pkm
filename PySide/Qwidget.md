تا جایی که من متوجه شدم کلاس `QWidget` که در ماژول `QtWidgets` قرار داره مثل یک کامپوننت مستقل عمل می کنه. این ویجیت می تونه هر نوع ویجیتی رو در داخل خودش نگه داره. 
در واقع کمی قدرتمندتر از ویجیت فریم در تی کی اینتر هست. 

```python
import sys
from PySide6 import QtWidgets




class HelloWorld(QtWidgets.QWidget):
    def __init__(self):
        super().__init__()

        # create label
        self.text = QtWidgets.QLabel("Hello World!")
        self.button = QtWidgets.QPushButton("Click Me")

        # create vertical layout
        self.vlayout = QtWidgets.QVBoxLayout(self)
        self.vlayout.addWidget(self.text)
        self.vlayout.addWidget(self.button)

        # button on click event.
        self.button.clicked.connect(self.change_message)

    def change_message(self):
        self.text.setText("Salam donya")


if __name__ == "__main__":
    app = QtWidgets.QApplication([])

    widget = HelloWorld()
    widget.resize(800, 600)
    widget.show()

    sys.exit(app.exec())
```
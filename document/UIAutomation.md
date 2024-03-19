# Input methods

Whenever we insert data into an application or send a command to a system to produce a change or continue, we perform an input action.

Modern design experiences use four input methods:
- Hardware Events
- SendWindowMessages
- Simulatie
- Chromium API

## Hardware Events

- Hardware events are essentially the actions we perform using our keyboard or mouse, such as clicking or typing. These actions are captured by the operating system and can be used by UiPath to simulate user interactions with an application.
- When we use the hardware events input method in UiPath, it directly interacts with the hardware device (mouse or keyboard) by sending messages to the operating system. This means that when we click, the mouse cursor moves across the screen and when we type, the keyboard driver is used to type individual characters.
- One important thing to note is that hardware events are compatible with all applications but do not work in the background. This means that the attended user cannot touch the mouse or keyboard during the automation.

Use case: this input method is useful for automating simple tasks that involve keyboard and mouse interactions, such as data entry or clicking buttons. It is also useful for automating applications that are not compatible with other input methods, as it can interact with any application. 

## SendWindowMessages

- It simulate user interactions with an application. 
- When you use this input method, UiPath sends the same messages to an application that the application would receive if a user were to interact with it using a keyboard or mouse. This means that UiPath is essentially controlling the application in the same way that a user would. 
- The benefit of using Send Window Messages is that it allows the automation to work in the background without interfering with the user's ability to use their computer.

Use case : this input method is useful for automating applications that require a high level of accuracy or timing, as it can directly communicate with the application's window. It is also useful for automating applications that do not respond to other input methods. 

## Simulatie

- Simulate input method designed to mimic our actions in a way that's similar to how we would interact with the application. This means that instead of relying on low-level hardware events or window messages, Simulate can interact with UI elements directly.
- By doing this, the robot can perform actions such as clicking a button or typing in a text box more accurately and consistently.

- Additionally, using Simulate is often faster than using hardware events or window messages, and allows the robot to interact with an application in the background while we perform other tasks.

- It's important to note, however, that not all applications are compatible with Simulate. In these cases, it's important to choose the input method that works best for the specific application being automated.

Use case: this input method is useful for automating tasks that involve interacting with graphical user interfaces (GUIs), such as clicking buttons or typing in text boxes. It is also useful for automating tasks that need to be performed quickly and accurately.

## Chromium API

- ChromiumAPI is an input method used for browser automation, and it's based on the Devtools protocol. It's compatible with all Chromium-based browsers, such as Chrome or Edge. Basically, it can be used for any website or application that runs inside the Chromium browser.
- ChromiumAPI supports several activities including Use Application/Browser, Click, Type Into, Hover, and Keyboard Shortcuts.

- It uses direct communication with the browser, which means there are fewer communication channels and increased automation reliability.

- One of the advantages of using ChromiumAPI is that it works in the background, allowing users to work on other activities while the automation is executing.

Usecase: this input method is useful for automating tasks that involve interacting with web applications, as it can directly communicate with the browser's Devtools protocol. It is also useful for automating tasks that need to be performed in the background, such as web scraping or monitoring web pages.

## Differences between each iinput method
|input Method|Compatibility|Backgournd Execution|Speed|Hotkey Support|Auto Empty Field|
|--|--|--|--|--|--|
|Hardware Events|100% - all types of applications.|No|50%|Yes|No|
|SendWindowMessage|80%|Yes|50%|Yes|No|
|Simulate|99% - Web apps <br> 60% - desktop apps|Yes|100%|No|Yes|
|ChromiumAPI|100% - Chrome and Edge browsers|Yes|50%|Yes|Yes|

# Foreground and Background moode

Foreground processes are things you are currently using on your computer, such as documents or web browsers, for which you can see and interact with your screen. 

Background processes, on the other hand, run on your computer without your involvement. 

## Background Mode

Background mode allows data to be input into an application or browser without requiring active user interaction, operating as a background process.

## How does the Background mode work

The Background mode runs all the activities inside the "Do" block of the "Use application browser" card in the background, using either Simulate or ChromiumAPI as an input method.

However, it's important to keep in mind that the Background mode isn't a foolproof solution, as certain UI actions aren't compatible with it.

The following actions aren't compatible with the Background mode:

- Any activities using image as targeting method.
- Native text automation.
- Keyboard shortcuts.
- Minimizing opened applications.
- The Take Screenshot Activity.

## What if the automation includes incompatible actions for Background mode?

It'll run smoothly, but incompatible activities will run in the foreground. However, after the execution, it'll return to the background.

# Output methods

Output actions are used to extract data, generally in the form of text, from UI elements. Output methods are how output actions extract data from UI elements.

- Full Text
- Native
- Optical character recognition (OCR)

## Full Text
The FullText method is the default method and good enough in most cases. It is the fastest, it can extract hidden text, it has 100% accuracy, and can work in the background.

## Native
The Native method is compatible with applications that use Graphics Design Interface (GDI), the Microsoft API used for representing graphical objects. It doesn’t extract hidden text and it cannot work in the background; and just like FullText, it doesn’t support virtual environments.

## OCR
OCR (or Optical Character Recognition) is the only output method that works with virtual environments and with “reading” text from images. Its technology relies on recognizing each character and its position. On the other hand, it cannot work in the background, it cannot extract hidden text, and its speed is by far the lowest.

## Differences between these output mehtods

|Output method|Full Test|Native|OCR|
|--|--|--|--|
|**Default method and Compatibility**|It is the Default method and good enough in most cases.|Compatible with applications that use Graphics Design Interface (GDI), the Microsoft API is used for representing graphical objects.|OCR (or Optical Character Recognition) is the only output method that works with virtual environments and with “reading” text from images.<br>Its technology relies on recognizing each character and its position.|
|**Automation Speed**|Fastest compared to the other two methods.|Somewhat slower than FullText.| By far the slowest.|
|**Accuracy**|100% accuracy.|100% accuracy on the applications that support GDI.|Accuracy varies from one text to another, by changing the settings we can improve the results.|
|**Running in Background**|Works in the background.|Cannot work in the background.|Cannot work in the background.|
|**Hidden Text**|Yes<br> (for example, the options in a drop-down list).|No|No|
|**Virtual Environment** |No|No|Yes|
|**Text position and formatting**|No|Yes|Yes|
|**Other**|The method offers the option to ignore the hidden message and capture only the visible text.|By default, it can process all known characters as separators (comma, space, and so on), but when only certain separators are specified, it can ignore all the others.|The OCR method has two default engines that can be used alternatively:<br>- Google Tesseract<br>- Microsoft MODI.|


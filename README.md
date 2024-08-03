<h1>Key Word Spotting on Arduino Nano 33 BLE</h1>

<b>In this project I will demonistrate the steps, for ML workflow, KWS application arcitecture and deployment. ML workflow loops through collecting a data and making inferences, with more steps in between as shown below. It incorporates, loss functions, data augumentation, gradient descent, regression, classification, quantization, optimization, pruning, filters, neural networks, pre-processing, inferences, and post-processing steps.</b>

<img width="620" alt="image" src="https://github.com/user-attachments/assets/6f732903-70e6-4ff0-a8bf-e3275b35222a">


<b>Key word Spotting application architecture has 4 distinct steps, Initialization, pre-processing, inference, and post-processing.</b>
- Initialization has many steps, first we have to declare the variables, then load the data with "g-model" function, choose resolve operators, initialize interpreter, allocate arena for memory, define model inputs, then we will set up the main loop.
- Pre-processing is part of the main loop, performed before inference. It involves Audio provider and feature extractor.
- Inference is also part of the main loop comes nest to the pre-processing where we prepare input tensors and invoke interpreters. we just have to make sure the input buffers are set up properly.
- post-processing is done to make sure that we have confidence in our results. Command recognizer and command responder is used for this step.
<img width="464" alt="image" src="https://github.com/user-attachments/assets/8cf273c5-bdda-475a-904f-feff69b87ed1">

<h2>Deploying the Pretrained KWS Model</h2>
<b> With the above steps I could be able to pretrain my model, now I will deploy it to my Arduino nano 33 BLE microcontroller via Arduino IDE.</b>

<h2>Load the pretrained Tensorflow Lite model</h2>

<img width="677" alt="image" src="https://github.com/user-attachments/assets/320c0010-e6d8-4f85-9efb-657e40e411dc">

<h2>Generate a TensorFlow Lite for Microcontrollers Model</h2>
<b>To convert the TensorFlow Lite quantized model into a C source file that can be loaded by TensorFlow Lite for Microcontrollers on Arduino we simply need to use the xxd tool to convert the .tflite file into a .cc file.</b>
<img width="649" alt="image" src="https://github.com/user-attachments/assets/77b4de85-0992-4c2f-97f4-577bd69a16d0">
<img width="623" alt="image" src="https://github.com/user-attachments/assets/6a5b0450-3bba-47fd-aa83-1b8be00dc401">
<img width="501" alt="image" src="https://github.com/user-attachments/assets/bb198b0c-de69-42ea-a3a8-f9b2afb85381">
<b>Next I'll Use a USB cable to connect the Arduino Nano 33 BLE Sense to my machine. I should see the green LED power indicator come on when the board first receives power</b>
- I will first Select the Arduino Nano 33 BLE as the board by going to Tools → Board: <Current Board Name> → Arduino Mbed OS Boards (nRF52840) → Arduino Nano 33 BLE.
- Then, I'll select the USB Port associated with my board. This will appear differently on Windows, macOS, Linux, but will likely indicate ‘Arduino Nano 33 BLE” in parenthesis. I'll select this by going to Tools → Port: <Current Port (Board on Port)> → <TBD Based on OS> (Arduino Nano 33 BLE). Where <TBD Based on OS> is most likely to come from the list below where <#> indicates some integer number.






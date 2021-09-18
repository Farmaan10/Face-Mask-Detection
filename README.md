
# Face Mask Detection
Corona Virus Disease (COVID-19) pandemic has caused a health crisis. With the ongoing second-wave and the probable third wave arriving in the month of September/October, one of the effective methods against the spread of the virus is wearing a face mask. This project introduces face mask detection that can be used by the authorities to make mitigation, evaluation, prevention, and action planning against COVID-19. The face mask detection in this study is developed with a machine learning algorithm through the image classification method: MobileNetV2. The steps for building the model are collecting the data, pre-processing, split the data, testing the model, and implement the model. The built model can detect people who are wearing a face mask and not wearing it at an accuracy of 99.63%. This speed & accuracy of the model compared to the counterpart classification methods is much more.

## MobileNetV2
The MobileNetV2 architecture is based on an inverted residual structure where the input and output of the residual block are thin bottleneck layers opposite to traditional residual models which use expanded representations in the input an MobileNetV2 uses lightweight depth wise convolutions to filter features in the intermediate expansion layer. Additionally, we find that it is important to remove non-linarites in the narrow layers in order to maintain representational power.

We demonstrate that this improves performance and provide an intuition that led to this design. Finally, our approach allows decoupling of the input/output domains from the expressiveness of the transformation, which provides a convenient framework for further analysis

![MNV2 Architecture](https://user-images.githubusercontent.com/68768741/133896369-3e6ae13e-d653-49d8-9070-fe4bcf357110.png)

![MNV2 Mathematical Architecture](https://user-images.githubusercontent.com/68768741/133896362-7147f220-42ce-4160-9e2b-c16010794daf.png)

## Block Diagram
![General Architecture](https://user-images.githubusercontent.com/68768741/133896368-3f7d74a0-c1c8-457b-a318-32a2e8f87aa6.png)

## Algorithm
![Algorithm](https://user-images.githubusercontent.com/68768741/133896419-5d06bdc5-9fd9-485a-b65b-0cff5ad33177.png)

### Training Phase:
1. First, we have all the photos in a folder and we import that folder.
2. There are two folders inside it, one with photos where people have masks on and the other where people who do not have their mask on.
3. These two types of folders act as tags for us, i.e., the people with mask and without mask. These two helps us training for our two specific purposes, to detect people with masks (training with the masked photos) and to detect people without masks (training with the photos without mask).
4. We save this trained model in our disk for future testing purposes.

### Applying Face Masks:
1. Loading the pre saved model from our disk so that we can use it for testing rounds.
2. Start the video stream using Imutils.
3. Detection of face using the camera.
4. Extraction of face from the view of the camera.
5. Applying the model and testing the input which we got from the camera and finally showing two values.
6. The first value will be the confidence percentage of the person wearing the mask, and the second value will be the person not wearing the mask.
7. We display the value at the end as our prediction, depending on which value is higher.
8. If the person is not wearing a mask, we save the picture of that particular person, so that we can identify that person and not save the picture otherwise (if they are wearing a mask). 

### Explanation and complete description:
The basic Idea behind our project is to make a facial mask detector that can be used in apartments, offices, etc. through the CCTV cameras to later catch and penalise people who were not wearing masks.
The main innovation in our project and difference between our product and any other product is that our product is dynamic. That is, it shows results on the display screen in real time and clicks(single) pictures of people who are not wearing a mask.
This will instil a fear of penalty among people and make them follow rules. This will help in creating a healthier work space environment in the industrial/office areas. Also, it will help in maintaining a healthier and safer society to live in.

## Results
![Results_mask](https://user-images.githubusercontent.com/68768741/133896752-17829921-6b9b-4308-9e1c-6bc09d108ff4.png)
Above, I'm wearing a mask. Using the webcam of the laptop as input. The mask worn is correctly confirmed by our model, which means it is successful in its first test, which was to identify correctly if a person has his/her mask on. The confidence level of the prediction, which is clearly very high at about 99.99%, and is very much in compliance with the industrial standards.

![Results_nomask](https://user-images.githubusercontent.com/68768741/133896750-b1a8bd5d-b319-4006-b9fb-df1f07a6dc34.png)
Here, the model correctly identifies me without a mask, which fulfils its second objective, which is to identify the person if he/she is not wearing the mask. The confidence level of the prediction, which is clearly very high at about 99.96%, and is very much in compliance with the industrial standards.

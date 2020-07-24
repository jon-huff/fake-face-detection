Python notebook to be added soon:

Implementation of the Kaggle Real and Fake Face Detection challenge:
https://www.kaggle.com/ciplab/real-and-fake-face-detection

The motivation for this challenge came as a step towards building
expertise in the skills required for my independent capstone project
as a graduate student at The University of Chicago.  In this capstone,
we are focusing on detection methods for deepfake media.

The dataset consists of real and photoshopped faces of varying
difficulty/realness.  The data is labeled in terms of which facial
region was manipulated (left eye, right eye, nose, mouth).

The first step was to run the dataset through
both a pre-trained model (ResNeXt) in PyTorch, and then through a
custom built CNN architecture.  Both models yielded mediocre validation
accuracy.  

Next step involved training a YOLOv4 model to detect different facial
regions (eyes, nose, mouth), crop out these sections per the returned
bounding boxes, and feed them into a CNN model.  Because the cropped images
were of varying resolutions, I first tried utilizing a U-Net model which did
not require unifrom input resolutions as there are no linear layers at the
end of this network architecture.

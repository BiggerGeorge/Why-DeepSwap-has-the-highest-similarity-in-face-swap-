## What is face swap?
Face swap is a technique that uses artificial intelligence (AI) to super-impose a person’s face onto a photo or video while preserving the original face’s expressions, eye and mouth movements, pose, lighting, and background. 
 
The goal is to maintain the context of the rest of the body and environment.  

It is also performed on videos, and the same facial expressions, eye and mouth movements of the source are carried over to the target.  

## How does face swap work?
In the process of face-swapping, there are three objects involved:  

(1) **Target photo/video**, which is the material where you want to replace the face while keeping all other elements consistent.  

(2) **Source photo**, which is the source of the face you want to swap.  

(3) **Result photo/video**, which is the final product after the face has been swapped.

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/e3c67eb0-b583-4760-81e0-bf4299238fd1)

The process of face swapping is complicated. It involves several key steps:

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/e7de09a2-2dea-4066-a847-590774777aea)

**Step 1: Face Detection**

The first step is to detect and locate faces in the source and target images or videos. This is typically done using computer vision algorithms that identify facial features.

Several algorithms(especially the CNNs) can be used for face detection:

**Deep Learning (Convolutional Neural Networks — CNNs)**

**Training**: CNNs are trained in large datasets of images containing faces. The network learns to recognize the complex patterns and structures of faces.  

**Inference**: The trained CNN is used to predict the presence and location of faces in new images.  

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/bcab1433-800f-4c92-bb3f-94076ccda7c3)

**Step 2: Facial Landmark Detection**

Once faces are detected, the next step is to identify specific facial landmarks or key points.

CNNs or other deep learning models identify specific facial landmarks or key points, corresponding to important facial features like eyes, nose, mouth, and jawline.

Typical landmark detection models identify between 68 to 194 key points on a face.

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/9961fd1b-5f08-4f95-88b2-7fa1d5869c5f)

**Step 3: Face Alignment**

The detected faces are aligned based on the identified landmarks to ensure proper matching of facial features between source and target

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/ed61e502-6030-48dc-97c2-cfd16fc04305)

**Step 4: Feature Extraction**

Deep neural networks, often pre-trained on face recognition tasks, extract identity-related features from the source face

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/b6807bd3-918d-4430-8377-1308ac33bb49)

**Step 5: Attribute Encoding**

A separate network encodes attributes of the target face, such as pose, expression, and lighting conditions.

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/40437b5d-821d-45a1-a5ad-3288a0314f6f)

**Step 6: Face Generation**

A generator network, typically based on generative adversarial networks (GANs) or autoencoders, combines the identity features from the source face with the attributes of the target face to generate the swapped face.

**Step 7: Blending**

The generated face is blended with the target image, often using techniques like adaptive attentional denormalization (AAD) to integrate identity and attributes seamlessly.

**Step 8: Refinement**

Additional networks may be used to refine the result, such as preserving occlusions or improving overall realism.

**Step 9: Video Processing**

For face swapping in videos, additional steps involve tracking facial movements frame by frame and ensuring temporal coherence.

**Step 10: Training**

The entire system is typically trained end-to-end using large datasets of face images, often employing techniques like progressive training to achieve high-resolution results.  


## How to evaluate a face swap?

There are many factors to evaluate a face swap but one of the most important ones is to measure how similar the source and the result

When we compare how similar two images are, we turn the images into a set of numbers (feature vectors) that represent their key features.

These numbers are like a special code that tells us what’s in the image.

We then compare these codes using something called cosine similarity, which is like measuring how close together two arrows are pointing.

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/3988eb6f-cdee-431a-9a9f-5cb90dec7f6a)

If the arrows point of cosine similarity in almost the same direction, it means the images are very similar.

If the arrows point in opposite directions, it means the images are very different.

When we say the cosine similarity is 0.9, it’s like saying the arrows are pointing very close to each other, which means the images have a lot of the same features and look quite alike.

So, a cosine similarity of 0.9 between two images tells us that they look very similar to each other.

## DeepSwap has the highest similarity in industry

Unlike other services and products that use open-source AI models, DeepSwap has developed its own AI model over many years.

It has been trained on more than 50,000 images from public datasets such as CelebA and LFW, using data augmentation techniques like rotation, cropping, and color transformation to enhance the diversity of the data.

When I tested the similarity of DeepSwap’s face-swapping, I used Pytorch InsightFace to calculate the loss function after the face swap.

https://github.com/nizhib/pytorch-insightface?source=post_page-----8a5c50a34513--------------------------------

**After long time test, on average, DeepSwap’s loss function is only 0.06, which means the similarity of its face-swapping effect reaches 1–0.06 = 0.94, or 94%.**

Typically, if the similarity exceeds 80%, it becomes quite difficult for the human eye to recognize the differences.

If the number surpasses 90%, the result is virtually indistinguishable from the original person.

In contrast, general open-source models usually achieve a similarity of about 60% to 70%.

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/204e6d49-d608-49cb-bc60-432aa6ac363c)

![image](https://github.com/BiggerGeorge/Why-DeepSwap-has-the-highest-similarity-in-face-swap-/assets/171020335/035f340b-24e6-4e37-9218-c2f77e2c5d24)




# <b><i>Foliage Disease Classification</b></i>
Now Let me take you along a journey on finding the right model for the task. It started with MobileNet vs efficientnet, finally deciding to move forward with efficientnetb4. That was a mistake, while the model has only 19.3 million parameters it still was not quite computationally efficient enough for the task! Then comes efficientnet v2 small containing nearly 22 million parameters but an improved speed on training times and improved accuracy. I then compared this model side by side against mobile ViT. 

## Here are the results:
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Model</th>
      <th>Final Accuracy</th>
      <th>Training Time</th>
      <th>Parameters</th>
      <th>Throughput</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>EfficientNetV2-S</td>
      <td>91.54%</td>
      <td>2817.9s</td>
      <td>20,269,720</td>
      <td>822.2 samples/sec</td>
    </tr>
    <tr>
      <td>MobileViT</td>
      <td>89.61%</td>
      <td>2826.6s</td>
      <td>1,960,568</td>
      <td>819.6 samples/sec</td>
    </tr>
  </tbody>
</table>

That was not enough to convince me to use efficientnet v2s. Yes it is a fantastic SOTA model but still required more resources which is why I started looking more into the mobile Vit models and found mobileViT v2 had about 3 million parameters which provides more room if Id like to include something like segmentation that could potentially take up more resources. 
<br></br>

# What's that plant disease!? It's early blight!
Open Google Colab for live demo using MobileViT v2 classify disease
on your own image (will provide what plants it will be capable of analyzing soon!)

## <b>Example from the project:</b>
GradCam was utilized to understand what MobileViT v2 was focusing on. 

<img width="1957" height="985" alt="gradCam" src="https://github.com/user-attachments/assets/3f1a53fd-7f78-461f-bdf0-c50a5cbecc8a" />

## Why MobileViT v2? 
* lightweight
* easy to train
* closer to traditional cnn than v1

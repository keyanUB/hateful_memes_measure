# hateful_memes_measure
 
## Image Result from Different APIs:

### The Total Pass Rate (False Negtive)
- Pass rate = (predict safe) / (real unsafe) = 1129 / 1341 = 84.19\%

### The Total False Rate (False Positive)
- False rate = (predict unsafe) / (real safe) = 587 / 3659 = 16.04\%

### Safe Lables Classification Report
| APIs | precision | recall | f1-score | 
| --- | --- | --- | --- |
| **Google Cloud Vision** |0.7332 | 0.9719 | 0.8358 |
| **Amazon Rekognition** | 0.7331 | 0.9932 | 0.8435 |
| **Clarifai NSFW**  | 0.7328 | 0.9954 | 0.8441 |
| **DeepAI NSFW** | 0.7323 | 0.9913 | 0.8423 |


### Not-Safe Lables Classification Report
| APIs| precision | recall | f1-score | 
| --- | --- | --- | --- | 
| **Google Cloud Vision**| 0.3133| 0.0350 | 0.0630 |
| **Amazon Rekognition**| 0.4186 | 0.0134 | 0.0260 | 
| **Clarifai NSFW (0.4)**| 0.4333| 0.0097 | 0.0190 |
| **Clarifai NSFW (0.5)**| 0.0000| 0.0000 | 0.0000 |
| **DeepAI NSFW (0.4)** | 0.3191| 0.0112 | 0.0216 |
| **DeepAI NSFW (0.5)** | 0.2857| 0.0075 | 0.0145 |

### Evaluation Ouput
<img src="https://github.com/keyanUB/hateful_memes_measure/blob/main/img_result.png?raw=true" width="450">

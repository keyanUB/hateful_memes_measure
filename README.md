# hateful_memes_measure
 
## Image Result from Different APIs:

### Safe Lables Classification Report
| APIs | safe criteria | precision | recall | f1-score | 
| --- | --- | --- | --- | --- |
| **Google Cloud Vision** | possibility of all safety factors not bigger than 3 ('POSSIBLE') |0.7332 | 0.9719 | 0.8358 |
| **Amazon Rekognition** | score of 'hateful' < 0.5 (0\~1) | 0.7331 | 0.9932 | 0.8435 |
| **Clarifai NSFW**  | NSFW score < 0.5 (0\~1) | 0.7328 | 0.9954 | 0.8441 |
| **DeepAI Content-moderation** | NSFW score < 0.5 (0\~1) | 0.7323 | 0.9913 | 0.8423 |


### Not-Safe Lables Classification Report
| APIs| not-safe criteria | precision | recall | f1-score | 
| --- | --- | --- | --- | --- |
| **Google Cloud Vision**| possibility of any safety factor >= 4 ('LIKELY') | 0.3133| 0.0350 | 0.0630 |
| **Amazon Rekognition**| score of 'hateful' >= 0.5 (0\~1) |0.4186 | 0.0134 | 0.0260 | 
| **Clarifai NSFW (0.5)**| NSFW score >= 0.5 (0\~1) | 0.0000| 0.0000 | 0.0000 |
| **DeepAI Content-moderation (0.5)** | NSFW score >= 0.5 (0\~1) | 0.2857| 0.0075 | 0.0145 |

#### Google Cloud Vision API:
- Safety factors: "safe.adult", "safe.medical", "safe.spoofing" (ignored),"safe.violence", "safe.racy".
- Likelihood levels: 1 -UNKNOWN, 2 -VERYUNLIKELY, 3 -UNLIKELY,4 -POSSIBLE, 5 -LIKELY, 6 -VERYLIKELY.
- Criteria:   We  define  the  image  is  ”not  safe”  if  any  of  the  factors’likelihood levels bigger than 3.
#### Amazon Recognition API:
- Safety factors:  "hate".
- Criteria:  We  define  the  image  is  ”not  safe”  if  the  API  detect  any "hateful" content.
#### DeepAI Content-moderation API:
- Safety factors: adult content, hate symbols, guns, and offensive wordsfound amongst text within images.
- Safety  score:   the  API  will  detect  all  factors  and  return  NSFW scores.
- Criteria:  We define the image is "not safe" if it’s NSFW score is notless than 0.5.
#### Clarifai NSFW API:
- Safety factors:  NSFW items.
- Safety  score: the  API  will  detect  the  NSFW  items  and  return NSFW scores.
- Criteria:  We define the image is ”not safe” if it’s NSFW score is notless than 0.5.

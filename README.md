# Multiple-choice-questions-generator-using-NLP

<img width="703" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/05dc9fd1-ceb3-41ea-b8e3-d4e6f76963ae">

### 🎯Problem statement: 
We are tasked with developing a solution that can automatically generate
objective questions with multiple correct answers based on a given chapter from a subject.
The generated questions should test the reader's understanding of the chapter and have
more than one possible correct answer to increase the complexity and challenge of the
questions.The generated questions should not only test the reader's comprehension of the
chapter but also encourage them to think beyond the surface level and explore different
perspectives and possibilities. Ultimately, the objective of this project is to develop a robust
and accurate solution that can aid educators in creating engaging and challenging
assessments for their students.

### 😎Preview: <br>

<b> Very long text </b> <br>
text_2 = "Elon Musk and Bitcoin: A Complex Relationship.The intersection of Elon Musk, the enigmatic billionaire entrepreneur, and Bitcoin, the groundbreaking cryptocurrency, has been the subject of much fascination, speculation, and scrutiny in recent years. Musk, known for his ventures like Tesla, SpaceX, Neuralink, and The Boring Company, has proven to be a polarizing figure in the world of finance and technology, with his tweets and actions having significant implications for the price and perception of Bitcoin. This narrative explores the multifaceted relationship between Elon Musk and Bitcoin, delving into key events, controversies, and the broader implications for the cryptocurrency landscape.Elon Musk: A Brief Overview.Before delving into Musk's connection with Bitcoin, it's essential to understand who Elon Musk is and his role in the tech and automotive industries. Born in South Africa in 1971, Musk displayed a prodigious talent for technology from a young age. He moved to the United States to attend the University of Pennsylvania, where he earned dual bachelor's degrees in physics and economics.Musk's entrepreneurial journey began with the creation of Zip2, a software company he co-founded in 1995,………………………………”  <br><br>
final_questions = get_mca_questions(text_2) <br>
for q in final_questions: <br>
    print(q) <br><br>

<b> Output </b> <br>
1. Along with spacex, neuralink and boring company, what is a notable venture of Elon Musk? <br>
(a)tesla <br>
(b)Musk <br>
(c)Prius <br>
(d)Nissan <br>
Correct answer is : (a)

2. The narrative explores the multifaceted relationship between elon musk and what? <br>
(a)Btc <br>
(b)Fiat <br>
(c)bitcoin <br>
(d)Cryptocurrency <br>
Correct answer is : (c) <br>

3. What is elon musk known for? <br>
(a)Other tweets <br>
(b)tweets <br>
(c)Reddit posts <br>
(d)Facebook posts <br>
Correct answer is : (b)

4. What type of investment did elon musk make? <br>
(a)elon musk <br>
(b)bitcoin investment <br>
(c)musk <br>
(d)tesla <br>
Correct answer is : (b)

5. What type of vehicle is elon musk known for? <br>
(a)Battery storage <br>
(b)electric vehicles <br>
(c)Internal combustion engines <br>
(d)Clean energy <br>
Correct answer is : (b)

### ✅Solution methodology:
Here the goal of the problem is a little complex, where developing a solution from scratch takes time and thorough training and fine tuning on certain domain specific data. Although there are many API's available like gpt-3 etc, as this problem is posed in the interest of production usage for any company, we cannot rely on external API's very much. But we have taken small pretrained models here and demonstrated the overall work flow of the project, how to develop the solution for this kind of a problem.
In the interest of time, here a model which generates multiple choice questions with a single answer is developed and further steps are given in the future scope of the problem, where more robust model for this particular task will be developed later.

### ⭐Procedure outline:
Very useful resource where the current solution is inspired from : https://www.youtube.com/watch?v=hoCi_bJHyb8
1. Given any article we will perform an Extractive summarization ( which means we pick out the important sentences as they are and form a summary ) or Abstractive summarization ( where we get the summary of the text with a slightly changed phrasing or rewriting of the sentences )
2. If we perform Extractive summarization, we will perform paraphrasing of sentences using a language model.
3. Then we will extract the keywords from the processed text using models like (YAKE, TopicRank, KeyBERT, Multi-partitite algorithm etc )
4. Then we will generate the questions about the extracted keywords by giving the processed text along with the keyword to the fine-tuned model.
5. Then we generate the distractors/wrong choices for the model using ( wordnet, sense2vec or word2vec etc). 
6. Now we got the question with the set of correct answer and also the wrong answers, so we will display the result.

### 🍕Useful illustrations in chronological order

#### 1. Generating distractors ( the wrong answers to the question but which are very similar to the answer ) using wordnet

<img width="336" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/9b624466-20cd-4b8f-8959-31df6b9e3caa">

#### 2. Word sense disambiguation

<img width="697" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/f649a069-bc2f-4b5b-91c0-7a35fde8d6b1">

#### 3. BERT word sense disambiguation

<img width="592" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/46355729-a2ff-4bae-8d92-a601ea54b26d">

#### 4. Generate Questions using T5 transformer model

<img width="666" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/f1a087a1-1a5b-438f-a0ba-73cf39ff47cf">

#### 5. Squad dataset used for training

<img width="688" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/14d7b663-d419-4164-ba69-478d71f60233">

#### 6. Generating MCQs from any content

<img width="650" alt="image" src="https://github.com/Rohan-Thoma/Multiple-choice-question-generator-using-NLP/assets/98249384/27a184a8-363d-4674-82de-dbb27604d349">

### Useful Links and references
1. 🔗Connect with me on 🤝 LinkedIn : https://linkedin.com/in/rohan-vailala-thoma
2. 💼Check out my other case study blogs on 😎🤟🏻: https://medium.com/@rohanvailalathoma
3. 🏅credits to Ramsri Gautam for this informative session: https://www.youtube.com/watch?v=hoCi_bJHyb8

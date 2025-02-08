Tag: [[LLM]]

 ![karpathy youtube video](https://youtu.be/7xTGNNLPyMI?si=nO44vWffgEqLBJBz)

Step 1: download the whole web and extract text, filter, morderate
Step 2: Convert plain text into token 
		Token is nothing but most commonly used characters grouped other gather 
		  Gpt 4o uses vocalbulary size of 100k

[tokenizer](https://tictokenizer.vercel.app)

Step 3: training a neural network
![[Pasted image 20250208194716.png]]


We know that correct answer is 3962, becvause it was next in the dataset, now we need to adjust and update the whole neural network mathematically , for it to give high probability for 3962

![[Pasted image 20250208195417.png]]

Parameters are completely randomly set at beginning
![[Pasted image 20250208195616.png]]


[Large language model visualization](https://bbycroft.net/llm)

## Inference 

![[Pasted image 20250208200620.png]]
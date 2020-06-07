<h1>Recommendation Systems</h1>
in this repo I am going to learn recommendation systems. this systems are used in many applications like marketing, youtube and etc.
there is lots of aproaches like content-based, matrix factorization, deep learning (softmax etc). i will check some of them.
some ready python packages for recommending is going to be tested... like surprise package

<h2>surprise package:</h2>
it's a simple package. ratings sould be in range of (1,4). there is some algorithms like SVD SVD++ in this package. 


<h2> Embedding: </h1>
embeddings is used in many places like embedding users/items or for encoding.
if Embedding notebook i used it for embedding pokemon types. there was 18 unique of type1 and 19 of type2 attribute.
this attributes where in string type. first i encoded theme in to integer type with help of sklearn.preprocessing.LabelEncoder .
then created a simple neural network with tf.keras:

<h3>Layer (type)              input           output</h3>   
poke_embedding (Embedding)   (1,18)           (1,3) 
flatten (Flatten)                             (None, 3)          
relu1 (Dense)                                 (None, 30)      
relu2 (Dense)                                 (None, 15)      
dense_5 (Dense)                               (None, 1)

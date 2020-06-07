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

<h3>Layer (type)-------------input----------- output</h3>   
poke_embedding (Embedding)---(1,18)----------(1,3) <br>
flatten (Flatten)----------------------------(None, 3)<br>
relu1 (Dense)--------------------------------(None, 30)<br>
relu2 (Dense)--------------------------------(None, 15)<br>
dense_5 (Dense)------------------------------(None, 1)<br>

and fit the data on this network. the X is type1 or typ2 and the y is Total attribute. after fitting, the embedding values are in embedding_layer so we first get this layer with model.get_layer and get weights from this layer with layer.get_weights.
the formule for choosing embedding size is min(nuniques/2, 50).


there is another type of embedding and it's for encoding users/items with latent attributes. it is used in collaborative filtering and matrix factorization. We have matrix of ratings (for example) and we create a embedding matrix bases on that.
suppose rating matrix is R(m,n): m users and n items, we can factorize it to U(m,d) I(n,d) that R = U*I' . based on this embedding, we can make recommendations. U and I are embbeding for users and items. 
matrix factorization could been done with SGD (stochastic gradient descent) or some ready modules in sk-learn or scipy.

# DS303-Project

Our project is based on the implementation of the following paper:
https://www.researchgate.net/publication/2948052_KNN_Model-Based_Approach_in_Classification?enrichId=rgreq-92a5cfc320880c44038866c3ce74908f-XXX&enrichSource=Y292ZXJQYWdlOzI5NDgwNTI7QVM6MTAyMDM5MDUyODgxOTMzQDE0MDEzMzk0MTQ4MzE%3D&el=1_x_2&_esc=publicationCoverPdf

KNN Model-Based Approach in Classification:  
The k-Nearest-Neighbours (kNN) method for classification is effective but slow and relies on selecting the right value for k. The paper proposes a new method that replaces the data with a kNN model, which automatically determines the value of k for each data point, making classification faster and more accurate.     

**Model Construction Algorithm:**

1. Select a similarity measure and create a similarity matrix from the given training dataset:
This step involves choosing a similarity measure such as Euclidean distance, cosine similarity, etc., to calculate the similarity between each pair of data tuples in the training dataset. The result is a similarity matrix that contains similarity scores between all pairs of data tuples.

2. Set to ‘ungrouped’ the tag of all data tuples:
Initially, all data tuples are marked as 'ungrouped', indicating that they are not yet assigned to any representative.

3. For each ‘ungrouped’ data tuple, find its largest local neighbourhood which covers the largest number of neighbours with the same category:
In this step, the algorithm iterates over all 'ungrouped' data tuples and identifies their local neighbourhoods. A local neighbourhood is a set of data tuples that are similar to the given data tuple and have the same class label. The algorithm identifies the local neighbourhood that covers the largest number of data tuples with the same class label as the given data tuple.

4. Find the data tuple di with a largest global neighbourhood Ni among all the local neighbourhoods, create a representative <Cls(di), Sim(di), Num(di), Rep(di)> into M to represent all the data tuples covered by Ni, and then set to ‘grouped’ the tag of all the data tuples covered by Ni:
This step involves finding the data tuple with the largest global neighbourhood among all local neighbourhoods. A global neighbourhood is a set of data tuples that are similar to the given data tuple and have the same class label, regardless of their proximity to the given data tuple. The algorithm creates a representative using the class label of the identified data tuple, the lowest similarity score to the identified data tuple among all data tuples in the global neighbourhood, the number of data tuples in the global neighbourhood, and a representation of the identified data tuple itself. The algorithm then sets the 'grouped' tag for all data tuples in the global neighbourhood to indicate that they are now represented by the created representative.

5. Repeat step 3 and step 4 until all the data tuples in the training dataset have been set to ‘grouped’:
This step repeats steps 3 and 4 until all data tuples in the training dataset have been assigned to a representative.

6. Model M consists of all the representatives collected from the above learning process:
The resulting model M consists of all the created representatives that represent the training dataset.

**Classification Algorithm:**

1. For a new data tuple dt to be classified, calculate its similarity to all representatives in the model M:
This step involves calculating the similarity score between the given data tuple and all representatives in the model M using the chosen similarity measure.

2. If dt is covered only by one representative <Cls(dj), Sim(dj), Num(dj), Rep(dj)>, viz the Euclidean distance of dt to dj is smaller than Sim(dj), dt is classified as the category of dj:
If the given data tuple is similar to only one representative, meaning the Euclidean distance between the given data tuple and the representative is smaller than the lowest similarity score of the representative, then the given data tuple is classified as the category of the representative.

3. If dt is covered by at least two representatives with different category, classify dt as the category of the representative with largest Num(dj), viz. the neighbourhood covers the largest number of data tuples in the training dataset:
If the given data tuple is similar to at least two representatives with different class labels, then the algorithm classifies the given data tuple as the category of the representative with the largest number of data tuples in its global

Members :    
K Sabita  210110068         
M Bhavana 210020078    
Harsh Bharadwaj 210020053






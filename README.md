<h1>Convolutional Neural Network to detect deforestation in the Amazon Rainforest</h1>

<p> This project is part of my final work as an Aerospace Engineering student, and it comprises the development of a convolutional neural network (CNN) capable of classifying SAR images of deforestation in the Amazon Rainforest. The database used to train the CNN was created using the imagery avaiable in the European Space Agency (ESA) portal <a href = 'https://scihub.copernicus.eu/dhus/#/home'>Copernicus</a>.</p>

<h2> Choosing the target area</h2>

<p> The target area was the region inside the municipality of São Félix do Xingu, in the state of Pará, Brazil, and the sensing was made in July 5th, 2021. This city is particularly suitable for this project since it is the number one in cumulative forest degradation up to 2020, according to the <a href='https://bit.ly/3vI7ix3'>National Institute of Space Research</a> (INPE). Around 24% of São Félix's territory (more than 83 thousands square kilometers, that is more than the territory of Austria) has already been deforested.</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/18638482/152596819-330381ea-d05c-4c22-9c69-347332af831a.png" width="300" height="300">
    
  <img src="https://user-images.githubusercontent.com/18638482/152597420-a09c0c51-02c8-41e2-b654-dbeb2de7dc5a.png" width="300" height="300">
</p>

<h2> Collecting de dataset </h2>

<p>Synthetic Aperture Array (SAR) imaging is a method of remote sensing that operates beyond the visible light spectrum, using microwaves to form the image. The radiation in this wavelength is less susceptible to atmospheric interference than in the optical range. This is particularly fitting for monitoring the Amazon Rainforest, a region considerably umid and prone to cloud formation in a great part of the year. The downside is that, alternatively, a SAR image is less intuitive to be interpreted by a human eye than an optical image.</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/18638482/152604971-766edac1-7e38-4a60-b6fc-49a7c75262ff.png" width="300" height="300">
    
  <img src="https://user-images.githubusercontent.com/18638482/152605002-8ec6798d-29b9-46ee-9dd0-5619883d35fb.png" width="300" height="300">
</p>

<p>In order to remove the aspect of a televison tuned to a dead channel, it is necessary to pre-process the colleceted images. More details on this process will be avaiable in a near future (when my work will be published by the library of Universidade de Brasília). For the time being, it suffices to say that the original image turned into 27 new image as the one that follows:</p>

<img src="https://user-images.githubusercontent.com/18638482/152607714-cb46ef39-1053-43ca-8401-cdc4ffa8d563.png">

<p>Everyone of these new images were sliced in small chunks, resulting in about 1800 samples that comprised the dataset to be used to train the neural network that has yet to be developed.</p>

<h2>Labelling the samples</h2>

<p>As the above picture can demonstrate, the resulting faux-colors of the pre-processing step highlight the contrast between the areas where the forest is preserved and those where there are deforestation hotspots. Using high-resolution optical images of the same region as a complementary guide, every sample was manually labeled as one of these four categories:
  
  <ul>
    <li>totally preserved, when there is no trace of deforestation;</li>
    <li>partially preserved, when there is some trace of deforestation, but the preserved prevail;</li>
    <li>partially deforested, when the deforested area is the prevailing feature;</li>
    <li>totally deforested, when there is no trace of preserved area.</li>
  </ul>

Later in the CNN trainin step it will be clearer that this categorization were not optimal, to say the least.

<h2> Developing de convolutional neural network</h2>

<p>CNN is a deep neural network specifically developed to be applied in the recognition of visual pattern. This architecture is made by two kinds of hidden layers:</p>

<ul>
  <li>a convolutional layer (as the name goes), that pass a small window (the filter) through the input image, making a convolutional operation (dot product) between the filter and every chunck of pixels comprised in the perception window;</li>
  <li>a pooling layer, that gets as an input the output of the convolutional layer and makes a dimensional reduction operation, normally a mean operation with a given number (2x2, 3x3, depending on the desired reduction) of inputs.</li>
</ul>
  
<p>These operations are well suited in finding patterns in a picture with a good amount of generalization in order to prevent overfitting. The CNN developed for this work can be seen in the following picture: </p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/18638482/152639736-c3ec64ae-5fc6-4597-98b1-da7f6bc185c2.png" width="300" height="300">
</p>

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

Everyone of these new images were sliced in small chunks, resulting in about 1800 samples that comprised the dataset to be used to train the neural network that has yet to be developed.

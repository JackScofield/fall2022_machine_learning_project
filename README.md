# fall2022_machine_learning_project


For running, you need to create a new environment in anaconda with importing the environment.yml file.

Datasets links (Datasets are too big to put in github):

Stage1: https://www.kaggle.com/datasets/ashwingupta3012/human-faces

Stage2: https://www.kaggle.com/datasets/nipunarora8/age-gender-and-ethnicity-face-data-csv

Stage3: https://www.kaggle.com/datasets/muhammeddalkran/masked-facerecognition

To be clear, for each notebook, they are required to run with tensorflow above 2.8

For notbook1: FaceDetector, the labeled datasets are private and the onwer does not wish to share. For testing case, you could ask me to share a small-sub dataset. The plotting is quite overfitting since it's running a very small dataset. The actual running parameters are stated in write up.

For notebook2: age_gender_race, after you trained with 100 epochs, the last coding box loaded the weights to run one more epoch for you to generate the recall value and precision. The recall value and precision use the tf.keras.metrics.Recall()/Precision(). You can change as you wish. The weighted cross entropy is removed from all three notebooks since it does not help the performance.

For notebook3: FaceRecognition,

data_augmentation = keras.Sequential(
  [
    layers.RandomFlip("horizontal_and_vertical",
                      input_shape=(224,
                                  224,
                                  3)),
    layers.RandomRotation(0.1),
    layers.RandomZoom(0.1),
  ]
)

has been removed since it does not improve the model but affects the model's performance. If you want to use it, you can run it and add data_augmentation in model sequentail to apply it.
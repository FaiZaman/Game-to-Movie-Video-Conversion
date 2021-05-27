# Game-to-Movie-Video-Conversion

This repository uses Deep Learning and Computer Vision to convert frames from video games into frames that appear to be from movies.

All models were run on Google Colab. The frame-to-frame model took about 12 hours to run 50 epochs, while the face-to-face models took 3 hours to run 300 epochs.

## Data Setup

In the file path initialisation near the top, set the main_path variable to be the directory of the notebook. The full (Google Drive) structure should be the following:

game_to_movie.ipynb
data/
- game/
    - faces/
    - frames/
    - frames_to_transform/
    - MafiaVideogame.mp4
- movie/
    - faces/
    - frames/
    - TheGodfather.mp4
    - TheIrishman.mp4
    - TheSopranos.mp4
frame_to_frame/
- game_train/
- game_test/
- movie_train/
- movie_test/
face_to_face/
- game_train/
- game_test/
- movie_train/
- movie_test/
models/
- frame_to_frame/
- face_to_face/
results/

An example (empty) directory has been included in the submission.
To extract frames and save them to these folders, run each consecutive cell.

## Models

The models are the following:

Frame to Frame: g2m_051.h5, m2g_051.h5
Face to Face: non_augmented_g2m_301.h5, non_augmented_m2g_301.h5
Augmented Face to Face: augmented_g2m_171.h5, augmented_m2g_171.h5 (the best performing model was at 170 epochs)

where g2m means game to movie and m2g means movie to game.
These are saved in this Google Drive folder:
https://drive.google.com/drive/folders/1gHmQ1N-hivNvXNH8zaiuXIaWhdlXiDAQ?usp=sharing

## Training

Run one of the training cells after running the pre-requisite cells to train the model - if there's an Out Of Memory error when training the face model, reduce the batch size on line 4 in the train() function to 16.

If you don't want to train the models, you can move the trained models from the Google Drive folder into the `data/models/..` folder.

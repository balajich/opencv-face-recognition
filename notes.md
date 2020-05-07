# References
    https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/
# environment setup
    source ~/.local/bin/virtualenvwrapper.sh
    source ~/.bashrc
    mkvirtualenv ofr -p python3
    workon ofr
    pip install opencv-contrib-python
    pip install imutils
    pip install scikit-learn
    
# Run
    python extract_embeddings.py --dataset dataset --embeddings output/embeddings.pickle --detector face_detection_model --embedding-model openface_nn4.small2.v1.t7
    python train_model.py --embeddings output/embeddings.pickle --recognizer output/recognizer.pickle --le output/le.pickle
    python recognize.py --detector face_detection_model --embedding-model openface_nn4.small2.v1.t7 --recognizer output/recognizer.pickle 	--le output/le.pickle --image images/adrian.jpg
### Classificação de imagens com Transfer Learning | TensorFlow for Poets 2

Acesse o [repositório original](https://github.com/googlecodelabs/tensorflow-for-poets-2) para informações oficiais.

Aqui eu armazeno os dados da rede neural treinada pelo Google Codelabs e retreinada por mim.

### Comandos necessários para o retraining
```
python scripts/retrain.py --image_dir YOUR_GENERAL_IMAGE_PATH_HERE

IMAGE_SIZE=224 
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"
python -m s.retrain --bottleneck_dir=tf_files/bottlenecks  --model_dir=tf_files/models/"${ARCHITECTURE}" --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" --output_graph=tf_files/retrained_graph.pb --output_labels=tf_files/retrained_labels.txt --architecture="${ARCHITECTURE}" --image_dir=YOUR_GENERAL_IMAGE_PATH_HERE

python -m scripts.label_image \    --graph=tf_files/retrained_graph.pb  \    --image=YOUR_PATH_TO_IMAGE_HERE
```

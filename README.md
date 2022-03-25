# Tracking-de-Pessoas-Grupo-5
Projeto desenvolvido na disciplina INE5443 - Reconhecimento de Padrões ministrada pelo Prof. Aldo Von Wangenheim

![alt text](https://github.com/Matheus-Lenzi/Tracking-de-Pessoas-Grupo-5/blob/master/apresentacaoImagem.jpg?raw=true)

## Estudo e teste de tracking de pessoas usando abordagens clássicas e com CNN em visão computacional

## Objetivos 
Os objetivos deste trabalho são explorar o tema de tracking de objetos, pessoas, em uma sequência de imagens através de duas abordagens, usando ferramentas de visão clássica e ferramentas de machine learning, CNN.

## Usando ferramentas de visão computacional Clássica 

[descrever o que foi feito]

## Usando ferramentas de visão computacional com machine learning

Para a abordagem usando ferramentas de machine learning, foram escolhidos os métodos de Tracking SORT e DeepSORT. Estes dois métodos foram estudados e suas principais características e funções foram abordadas. 

Por se tratar de dois algoritmos complexos, optou-se, para esse trabalho, utilizar de ferramentas já disponíveis de aplicação de DeepSORT com a seguinte [fonte](https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch).

o arquivo em google colab, Neural_Network.ipynb
, está neste repositório.

### Algoritmo implementado

Setup
Download data
Run inference on video
Show results

#### Setup 
Nesta parte é feito a importação dos pacotes necessários para a implementação e construção da rede inicial de detecção de pessoas e os algoritmos de traking.
```sh
!git clone --recurse-submodules https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch.git  
```
#### Download data

Nesta parte do código é feito o download da sequência de imagens que contém a movimentação do objeto de interesse, pessoas.

```sh
!git clone https://github.com/Matheus-Lenzi/Tracking-de-Pessoas-Grupo-5.git
```
Além disso, nesta etapa também é feito o download dos pesos da CNN já treinada para reconhecer objetos pessoas. Neste trabalho foi usado uma [YOLOv5](https://github.com/ultralytics/yolov5).

```sh
!wget -nc https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch/releases/download/v.2.0/crowdhuman_yolov5m.pt -O /content/Yolov5_DeepSort_Pytorch/yolov5/weights/crowdhuman_yolov5m.pt

```

#### Run inference on video

Nesta etapa é executado o script track.py e é passado como parâmetros os pesos da YOLOv5 que se pretende construir e o path da sequência de imagens na qual se tem interesse de estudo de rastreamento.
```sh
!python track.py --yolo_model /content/Yolov5_DeepSort_Pytorch/yolov5/weights/crowdhuman_yolov5m.pt --source /content/newOutput.mp4 --save-vid
```

#### Show results

Por fim, após o algoritmo de tracking ser executado, os resultados são carregados em HTML para serem mostrados usando a ferramenta notebook.

```sh
mp4 = open('output.mp4','rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
```
<div align="center">
<p>
<img src="Tracking-de-Pessoas-Grupo-5/ezgif.com-gif-maker (2).gif
" width="400"/> 
</p>

Principal fonte do código = [mikel-brostrom](https://github.com/mikel-brostrom/Yolov5_DeepSort_Pytorch)





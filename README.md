# Detector de gestos através de visão computacional

<img src="https://i.imgur.com/x8p2Ygk.jpg" width="250" height="250">

## Funcionamento do projeto

### Descrição

O seguinte projeto tem como foco detectar gestos da mão com a webcam e atribuir funcionalidades para as detecções, como mover personagem em um vídeo-game ou controlar peças de hardware.

### Arquivos com passo a passo

[ContinuousGesturePredictor.py](https://github.com/jaaoop/ProjectGestus/blob/master/ContinuousGesturePredictor.py) faz a detecção em tempo real dos gestos. 
1. Execute no terminal `python ContinuousGesturePredictor.py` .
2. Ao abrir o arquivo a webcam iniciará e a filmagem será mostrada ao usuário.
3. Na janela aberta um quadrado será desenhado e, durante 30 frames, pegará a área do desenho como *background*. Portanto, deixe essa área livre da mão para melhores resultados.
4. Após os 30 frames iniciais, a janela *Thresholded* irá aparecer, nesse momento o usuário deve apertar a tecla '**s**' para começar a detecção e, então, posicionar a mão no quadrado desenhado.
5. A janela *Statistics* aparecerá com o nome do gesto detectado, o usuário é livre para fazer movimentos e testar novas detecções.

[LabelGenerator.py](https://github.com/jaaoop/ProjectGestus/blob/master/LabelGenerator.py) gera novos gestos para treino.
1. Execute no terminal `python LabelGenerator.py`.
2. Ao abrir o arquivo a webcam iniciará e a filmagem será mostrada ao usuário.
3. Na janela aberta um quadrado será desenhado e, durante 30 frames, pegará a área do desenho como *background*. Portanto, deixe essa área livre da mão para melhores resultados.
4. Após os 30 frames iniciais, a janela *Thresholded* irá aparecer, nesse momento o usuário deve posicionar a mão no quadrado desenhado e apertar a tecla '**s**' para começar a gerar os gestos de treino e teste. **Sugestão:** Mova a mão para diversificar os resultados.
5. No processo de criação do novo gesto, o console irá mostrar o progresso. Ao finalizar, duas pastas serão criadas, uma em [Treino](https://github.com/jaaoop/ProjectGestus/tree/master/Dataset/Train) e uma de [Teste](https://github.com/jaaoop/ProjectGestus/tree/master/Dataset/Test), ambas com o nome do gesto.

[ModelTrainer.py](https://github.com/jaaoop/ProjectGestus/blob/master/ModelTrainer.py) treina o modelo para detectar novos gestos.
1. Certifique-se que possui as mesmas pastas em [Treino](https://github.com/jaaoop/ProjectGestus/tree/master/Dataset/Train) e [Teste](https://github.com/jaaoop/ProjectGestus/tree/master/Dataset/Test).
2. Execute no terminal `python ModelTrainer.py -g <numero de gestos>`.
3. Aguarde até o final do treinamento.
>**Nota:** Um parâmetro adicional ao ModelTrainer é `-c True` que permite salvar o gráfico de treino, por padrão é `-c False`.

## Recomendações ao usuário para utilizar o repositório
- Utilize o conda para criar ambientes virtuais.
- Use cuda e cudnn para ter um melhor desempenho (verifique se a GPU é compatível).
- Recomenda-se Linux para realizar os procedimentos.

## Instalação

### Python 

Recomenda-se versão 3.7.

### Crie um ambiente virtual com o conda

`conda create -n <nome-do-ambiente> python=3.7`<br/>
`conda activate <nome-do-ambiente>` 

### Dependências necessárias

- ### TensorFlow (recomenda-se versões <= 1.15.2)
`pip install tensorflow==1.15.2` (CPU)<br/>
`pip install tensorflow-gpu==1.15.2` (GPU)
- ### OpenCV
`pip install opencv-python`
- ### Numpy
`pip install numpy`
- ### Pillow
`pip install Pillow`
- ### Imutils
`pip install imutils`

## Informações
Este projeto é parte dos projetos da RAS Unesp Bauru. Para mais informações a respeito desse e outros projetos, acesse: https://sites.google.com/unesp.br/rasunespbauru/home.

## Autores

- [**Artur Starling**](https://github.com/ArturStarling)
- [**Fabrício Amoroso**](https://github.com/lefabricion)
- [**Gustavo Stahl**](https://github.com/GustavoStah)
- [**João Gouvêa**](https://github.com/jaaoop)

## Licença

Este projeto é gratuito e sem fins lucrativos. Sua venda é proibida.

## Creditos

O projeto foi baseado no repositório [Hand Gesture Recognition using Convolution Neural Network built using Tensorflow, OpenCV and python](https://github.com/SparshaSaha/Hand-Gesture-Recognition-Using-Background-Elllimination-and-Convolution-Neural-Network).

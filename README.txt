J’ai fait uniquement la question 1. Mais vous devriez regarder mon code avec méfiance. Ça marche, mais je ne suis pas certain, surtout qu’une époch prend 23 minutes (sur mon ordi avec cpu).

Dans un des fichiers, il est écrit que nous devrions avoir (Isaac m’a envoyé ces valeurs, je n’ai pas vérifié):

 RNN: train:  120  val: 157
 GRU: train:   65  val: 104
 TRANSFORMER:  train:  77  val: 152

Mais pour RNN (problème 1), j’obtiens seulement 390 avec la commande suivante (après 25 epochs et environ 11 heures):

“ python ptb-lm.py --model=RNN --optimizer=SGD_LR_SCHEDULE --initial_lr=1 --batch_size=16  --seq_len=35 --hidden_size=256 --num_layers=2 --dp_keep_prob=0.35 ”


Je n’ai mis aucun dropout (pour RNN Q1, je ne vois pas à quoi sert dropout.

Le principal problème avec Pytorch ici, c’est de bien comprendre comment fonctionne Adagrad. En d’autres termes, quoi utiliser pour comme blocs (torch.tensor, nn.Linear, …?) pour que Pytorch puisse bien faire le backprop automatiquement?

Тезисно:
Смысл GPT-2: у вас есть текст из n слов/токенов. Скроем k слов/токенов, например, последнее слово. 
Создать такую сеть, чтобы на выходе мы получили исходный текст.

Обзор статьи "Language Models are Unsupervised Multitask Learners" за авторством создателей сети GPT-2.
Ссылка: https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf

I. Представление входных данных.
Используется подход, являющийся неким средним между представлением на уровне букв и представлением на уровне словоформ:
частотные словоформы подаются как есть, а нечастотные - как последовательности букв и/или буквенных n-грамм.

II. Что такое "attention head"?
В языковых моделях типа Transformer пространство векторных представлений разбивается на подпространства, в рамках которых кластеризуются некоторые метамодели синтаксических связей, именуемых "головами". Данный термин не случаен и заимствован из лингвистики. В частности, термин "Вершинное маркерование" (от англ. Head-marking) сообщает нам о способе моделирования синтаксической связи: от вершины (головы) к зависимым словоформам. Таким образом, задача обучения нейросети GPT-2 сводится к метамоделированию таких "голов".

![Attention Head](/img/AttentionHead.png)

Выше приведен пример того, выделяются "головы" в механизмах самовнимания. Читать изображение необходимо следующим образом: для каждого слова слева необходимо определить, насколько оно обращает внимание на каждое слово справа, находящее не "ниже" него. Слово справа, обладающее наибольшим весом, выступает "головой" конкретному слову слева. Так, например, слово run является зависимым элементов синтаксической связи, где "головой" выступает слово dog.


Некоторые выводы об архитектуре Transformer и конкурирующих нейросетях, построенных на ее основе.

1. Для большинства задач NLP однонаправленность лучше двунаправленности.


Ссылки на статьи:

Jesse Vig / GPT-2 https://towardsdatascience.com/openai-gpt-2-understanding-language-generation-through-visualization-8252f683b2f8

DessertFlow / GPT-2 https://habr.com/ru/post/440564/

sim0nsays / Transformer https://habr.com/ru/post/341240/

Open Sourcing BERT: State-of-the-Art Pre-training for Natural Language Processing / BERT https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html

BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding / BERT https://arxiv.org/pdf/1810.04805.pdf

Transformer: A Novel Neural Network Architecture for Language Understanding / Transformer https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html

Jesse Vig / BERT https://towardsdatascience.com/deconstructing-bert-distilling-6-patterns-from-100-million-parameters-b49113672f77
https://towardsdatascience.com/deconstructing-bert-part-2-visualizing-the-inner-workings-of-attention-60a16d86b5c1

DessertFlow / BERT https://habr.com/ru/post/436878/

Language Models are Unsupervised Multitask Learners / GPT-2 https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf

Ссылки на исходники:

Keras-BERT / BERT https://github.com/CyberZHG/keras-bert/blob/630bda7f62bcf12a75324e75a19fe937f1ba3edc/tests/test_bert.py

TensorFlow-BERT / BERT https://github.com/google-research/bert

Keras-GPT-2 / GPT-2 https://github.com/CyberZHG/keras-gpt-2

Tensorflow-GPT-2 / GPT-2 https://github.com/openai/gpt-2/blob/master/src/model.py



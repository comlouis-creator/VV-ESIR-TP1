# Practical Session #1: Introduction

1. Find in news sources a general public article reporting the discovery of a software bug. Describe the bug. If possible, say whether the bug is local or global and describe the failure that manifested its presence. Explain the repercussions of the bug for clients/consumers and the company or entity behind the faulty program. Speculate whether, in your opinion, testing the right scenario would have helped to discover the fault.

2. Apache Commons projects are known for the quality of their code and development practices. They use dedicated issue tracking systems to discuss and follow the evolution of bugs and new features. The following link https://issues.apache.org/jira/projects/COLLECTIONS/issues/COLLECTIONS-794?filter=doneissues points to the issues considered as solved for the Apache Commons Collections project. Among those issues find one that corresponds to a bug that has been solved. Classify the bug as local or global. Explain the bug and the solution. Did the contributors of the project add new tests to ensure that the bug is detected if it reappears in the future?

3. Netflix is famous, among other things we love, for the popularization of *Chaos Engineering*, a fault-tolerance verification technique. The company has implemented protocols to test their entire system in production by simulating faults such as a server shutdown. During these experiments they evaluate the system's capabilities of delivering content under different conditions. The technique was described in [a paper](https://arxiv.org/ftp/arxiv/papers/1702/1702.05843.pdf) published in 2016. Read the paper and briefly explain what are the concrete experiments they perform, what are the requirements for these experiments, what are the variables they observe and what are the main results they obtained. Is Netflix the only company performing these experiments? Speculate how these experiments could be carried in other organizations in terms of the kind of experiment that could be performed and the system variables to observe during the experiments.

4. [WebAssembly](https://webassembly.org/) has become the fourth official language supported by web browsers. The language was born from a joint effort of the major players in the Web. Its creators presented their design decisions and the formal specification in [a scientific paper](https://people.mpi-sws.org/~rossberg/papers/Haas,%20Rossberg,%20Schuff,%20Titzer,%20Gohman,%20Wagner,%20Zakai,%20Bastien,%20Holman%20-%20Bringing%20the%20Web%20up%20to%20Speed%20with%20WebAssembly.pdf) published in 2018. The goal of the language is to be a low level, safe and portable compilation target for the Web and other embedding environments. The authors say that it is the first industrial strength language designed with formal semantics from the start. This evidences the feasibility of constructive approaches in this area. Read the paper and explain what are the main advantages of having a formal specification for WebAssembly. In your opinion, does this mean that WebAssembly implementations should not be tested? 

5.  Shortly after the appearance of WebAssembly another paper proposed a mechanized specification of the language using Isabelle. The paper can be consulted here: https://www.cl.cam.ac.uk/~caw77/papers/mechanising-and-verifying-the-webassembly-specification.pdf. This mechanized specification complements the first formalization attempt from the paper. According to the author of this second paper, what are the main advantages of the mechanized specification? Did it help improving the original formal specification of the language? What other artifacts were derived from this mechanized specification? How did the author verify the specification? Does this new specification removes the need for testing?

## Answers

1. En août 2003 a eu lieu un blackout au nord-est des USA : La cause profonde de la panne a été liée à une variété de facteurs, dont le fait que FirstEnergy n'ait pas élagué les arbres empiétant sur la ligne électrique à haute tension
- Un bug logiciel dans le système d'alarme d'une salle de contrôle de la FirstEnergy corp.
- Une fois déclenchée, la condition de course a provoqué le blocage du système d'alarme pendant plus d'une une heure
- Le serveur de secours est entré en action, mais il n'a pas pu suivre les données non traitées.
- les avertissements et les alarmes n'ont pas été déclenchés parce que les systèmes avaientluttaient pour traiter les anciennes données.
- les employés n'ont pas pris de mesures
- la panne s'est étendue à une vaste région

Le bug est donc global. Panne d'électricité généralisée le 14 août 2003
- On estime que 10 millions de personnes ont été touchées en Ontario et 45 millions de personnes dans huit états américains.

2. Ce bug est local.

3. Le but est de causer des bugs régulièrement en "cassant" la production de code pour vérifier l'abilité du système à réagir en mettant fin à une instance dans la production de façon aléatoire, ou bien en mettant hors-circuit une région entière ou en créant un retard artificiel, une latence auprès des clients pour voir comment ceux-ci réagissent, s'ils s'aperçoivent d'un changement de qualité, de définition et résolution en pixels. Pour résumer, on créer soi-même le chaos afin de mieux le contrôler par la suite, on anticipe de cette façon et on teste mieux notre système.

4. WebAssembly définit un format de code binaire portable et un format de texte correspondant pour les programmes exécutables ainsi que des interfaces logicielles pour faciliter les interactions entre ces programmes et leur environnement hôte. Rapidité, efficacité et portabilité - Le code WebAssembly peut être exécuté à une vitesse quasi-native sur différentes plates-formes en tirant parti des capacités matérielles communes.

5. Les comportements innatendus sont plus clairs et moins présents.

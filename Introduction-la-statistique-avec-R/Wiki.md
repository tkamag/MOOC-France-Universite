### Documents de synthèse en français

- [Aide mémoire en français des principales fonctions R](http://cran.r-project.org/doc/contrib/Kauffmann_aide_memoire_R.pdf) (PDF, 5 pages)

- [Aide-mémoire de statistique appliquée à la biologie](http://cran.r-project.org/doc/contrib/Herve-Aide-memoire-statistique.pdf) (PDF, 83 fiches en 134 pages)

### Site de référence rapide en anglais

- [Quick-R](http://www.statmethods.net/) : site web listant, par thème, les principales commandes R, exemples à l'appui

### Commandes pour répondre à des problèmes précis

**Comment retourner le nombre de NA dans describe ?** 

    n.miss <- function(x, na.rm=FALSE) sum(is.na(x))
    describe(c(1, 3, NA, NA, 1), num.desc=c("mean", "n.miss"))    

Explication : On définit simplement une fonction qui compte le nombre de valeurs manquantes dans une variable. L'argument na.rm=FALSE lors de la définition de la fonction est nécessaire pour outrepasser le comportement par défaut de la commande describe.numeric(), utilisée par describe() et qui impose la présence d'un tel argument.


  [1]: 

*** 

**Ajout de la moyenne sur une boite à moustaches** 

Exemple :

    sh <- read.csv2("satisfaction_hopital.csv")
    boxplot(sh$age,ylab="Age",col="grey",main="Distribution des âges")
    points(x=1,y=mean(sh$age,na.rm=TRUE),col="red",type="p",pch=23,cex=1,bg="red")
    


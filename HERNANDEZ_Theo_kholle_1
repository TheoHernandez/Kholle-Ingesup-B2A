#!bin/python36
#Description : Stocker des nombres dans un fichiers csv pour les utiliser avec differentes options
#Date : 21/11/2018
#Auteur : HERNANDEZ Theo

#
# Import
#
import argparse
import csv

#
# Variables
#
somme = 0
total_nombre = 0


#
# Script
#
parser = argparse.ArgumentParser(add_help=False)
parser.add_argument('-l', '--liste', help='Affiche la liste', action='store_true')
parser.add_argument('-a', '--ajouter', help='Ajoute des nombres',nargs='*')
parser.add_argument('-c', '--couper', help='Supprime les elements de la liste', action='store_true')
parser.add_argument('-s', help='Afficher un nombre selon loption : --max, --min, --moy, --sum', action='store_true')
parser.add_argument('--max', help='Affiche le nombre maximum', action='store_true')
parser.add_argument('--min', help='Affiche la valeur minimum', action='store_true')
parser.add_argument('--moy', help='Affiche la moyenne', action='store_true')
parser.add_argument('--sum', help='Affiche la somme', action='store_true')
parser.add_argument('-t', help='Trie la liste dans lordre croissant puis avec --desc en decroissant', action='store_true')
parser.add_argument('--desc', help='Trie la liste en decroissant. ', action='store_true')
parser.add_argument('--help', action='help', default=argparse.SUPPRESS, help="Affiche laide")
args = parser.parse_args()

if args.liste:
        with open('array.csv', 'r') as fichiercsv:
                reader = csv.reader(fichiercsv, delimiter=',')
                for row in reader:
                        print('Tableau des nombres')
                        print(' , '.join(row))

elif args.ajouter:
        with open('array.csv','a') as fichiercsv:
                for nombre in args.ajouter:
                        fichiercsv.write(nombre+',')
                        print('Lajout est effectuer')
elif args.couper:
        with open('array.csv', 'r') as fichiercsv:
                fichiercsv_str=''.join(fichiercsv.readlines()[:-1])
        with open('array.csv', 'w') as fichiercsv:
                fichiercsv.write(fichiercsv_str)
                print('La liste est bien supprimer')

elif args.s:
        if args.max:
                maximum = 0
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                for listestr in row:
                                        try:
                                                nombre = int(listestr)
                                        except:
                                                print("Resultat :")
                                        if nombre > maximum:
                                                maximum = nombre
                print('Le plus grand --> '+ str(maximum))

        elif args.min:
                minimum = 100
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                for listestr in row:
                                        try:
                                                nombre = int(listestr)
                                        except:
                                                print("Resultat")
                                        if nombre < minimum:
                                                minimum = nombre
                print('Le plus petit --> '+ str(minimum))

  elif args.sum:
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                for listestr in row:
                                        try:
                                                nombre = int(listestr)
                                        except:
                                                print("Resultat")
                                        somme += nombre
                print('La somme --> '+ str(somme-nombre))

        elif args.moy:
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                for listestr in row:
                                        try:
                                                nombre = int(listestr)
                                        except:
                                                print("Resultat")
                                        somme += nombre
                                        total_nombre += 1
                somme -= nombre
                total_nombre -= 1
                moy = somme/total_nombre
                print('La moyenne --> '+ str(moy))

elif args.t:
        array = []
        if args.desc:
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                array = row
                                print('Ordre decroissant')
                                print(sorted(array, reverse=True))
        else:
                with open('array.csv', 'r') as fichiercsv:
                        reader = csv.reader(fichiercsv, delimiter=',')
                        for row in reader:
                                array = row
                                print('Ordre croissant')
                                print(sorted(array))



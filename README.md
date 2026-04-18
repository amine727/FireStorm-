# 📄 README – LAB 18 : FireStorm

## 🎯 Objectif
L’objectif de ce challenge est d’analyser une application Android afin de récupérer un flag en combinant :
- Analyse statique (Jadx)
- Analyse dynamique (Frida)
- Interaction avec Firebase

---

## 🧰 Outils utilisés
- Jadx (reverse engineering)
- Frida (instrumentation dynamique)
- ADB
- Python (pyrebase)

---

## 🧪 Étape 1 : Analyse statique

Analyse de l’APK avec Jadx.

On identifie :
- la classe principale : `MainActivity`
- une fonction critique : `Password()`
- utilisation d’une librairie native (`libfirestorm.so`)

👉 Le mot de passe est construit dynamiquement et partiellement en code natif.

---


## ⚙️ Étape 2 : Analyse dynamique avec Frida

L’objectif est d’exécuter dynamiquement la fonction `Password()`.

### ▶️ Lancement de frida-server

<img width="1131" height="234" alt="11" src="https://github.com/user-attachments/assets/51955325-1d30-453e-892b-dbbf40633af8" />

---
### ▶️ Script Frida
<img width="971" height="519" alt="13" src="https://github.com/user-attachments/assets/6a1bdef6-4066-4d28-a3bb-b215b8dcab9c" />



### ▶️ Résultat
<img width="1368" height="421" alt="12" src="https://github.com/user-attachments/assets/c37de2fd-36c9-43f8-87e4-0865cdcb8d41" />

👉 Mot de passe récupéré :  C7_dotpsC7t7f_._In_i.IdttpaofoaIIdIdnndIfC

## 🔐 Étape 3 : Exploitation Firebase

Utilisation du mot de passe avec un script Python pour s’authentifier et récupérer le flag.

---

### 📸 Capture – Script Python
<img width="865" height="645" alt="14" src="https://github.com/user-attachments/assets/4d36b784-6139-4eaa-9f14-834786cc16d3" />

---

### 📸 Capture – Résultat final
<img width="1009" height="121" alt="15" src="https://github.com/user-attachments/assets/0a48aba4-bfcc-484a-93be-9de734b780cd" />

👉 Flag obtenu :  PWNSEC{C0ngr4ts_Th4t_w45_4N_345y_P4$$w0rd_t0_G3t!!!OR!5_!t???}

## 🧠 Conclusion

Ce challenge démontre :
- L’importance de l’analyse statique
- L’utilisation de Frida pour contourner le code natif
- L’exploitation d’un backend Firebase
- La combinaison de plusieurs techniques d’analyse



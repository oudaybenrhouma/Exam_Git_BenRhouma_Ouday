# 1. Create a GitHub repo named Exam_Git_Nom_Prenom with README.md
# (done on GitHub website with "Add README" checked)

# 2. Clone the repository locally
git clone https://github.com/<your-username>/Exam_Git_Nom_Prenom.git
cd Exam_Git_Nom_Prenom

# 3. Configure git username and email
git config --global user.name "Nom Prenom"
git config --global user.email "email@example.com"

# 4. Add .gitignore for Python temporary files
echo "*.pyc" >> .gitignore
echo "__pycache__/" >> .gitignore

# 5. Add config.txt with project description
echo "Description du projet: Application de gestion utilisateur." > config.txt

# 6. Commit and push initial configuration
git add .
git commit -m "Ajout de la configuration initiale"
git push origin main

# 7. Create and switch to branch feature_user
git branch feature_user
git checkout feature_user

# 8. Add user.py with greeting
echo 'print("Bonjour, Nom")' > user.py

# 9. Commit changes
git add user.py
git commit -m "Ajout du module utilisateur"

# Push the branch
git push origin feature_user

# 10. Return to main and modify config.txt
git checkout main
echo "Nouvelle ligne de configuration." >> config.txt
git add config.txt
git commit -m "Mise a jour du fichier config"

# 11. Merge feature_user into main
git merge feature_user

# Push updated main
git push origin main

# 12. Delete feature_user branch locally and remotely
git branch -d feature_user
git push origin --delete feature_user

# 13. Create feature_log branch and add log.py
git checkout -b feature_log
echo 'with open("app.log","a") as f: f.write("Action utilisateur\n")' > log.py
git add log.py
git commit -m "Ajout du module de journalisation"
git push origin feature_log

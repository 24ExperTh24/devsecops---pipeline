# Devsecops – Pipeline 

Γενική Επισκόπηση του Workflow
Το παρακάτω GitHub Actions workflow: https://github.com/24ExperTh24/docker-scan-pipeline/actions/runs/13823329708 σκανάρει το Docker image: Debian: bullseye για ευπάθειες χρησιμοποιώντας την Docker Scout (ένα εργαλείο για ανίχνευση CVEs - Common Vulnerabilities and Exposures).
•	Το workflow ενεργοποιείται όταν υπάρχει push στο main branch. Αυτό σημαίνει ότι το pipeline θα τρέχει μετά από κάθε αλλαγή που κάνω στο βασικό branch του repository (main).
•	Συνδέομαι στο Docker Hub, καθώς το pipeline συνδέεται στο Docker Hub χρησιμοποιώντας αποθηκευμένα credentials για να αποκτήσει πρόσβαση στα Docker images. Τα στοιχεία username και password ανακτώνται από τα GitHub Secrets που έχω ορίσει για τον λογαριασμό μου στο Docker Hub (DOCKER_USERNAME και DOCKER_PASSWORD).
•	Χρησιμοποιείται το docker/scout-action για την ανίχνευση ευπαθειών.
•	Η παράμετρος command: cves ζητά από το Docker Scout να αναγνωρίσει γνωστές ευπάθειες CVEs που σχετίζονται με το συγκεκριμένο image. 
•	Όταν ολοκληρωθεί το workflow, το GitHub Actions εμφανίζει τα αποτελέσματα της σάρωσης για ευπάθειες στο Docker image.

sudo docker build -t container-harbor.container.it-scholar.com/dataport/ben-coeppicus:v2 .

sudo docker push container-harbor.container.it-scholar.com/dataport/ben-coeppicus:v2 

sudo docker compose up -d

sudo trivy image container-harbor.container.it-scholar.com/dataport/ben-coeppicus:v2 
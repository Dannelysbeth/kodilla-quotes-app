### 1. Runnning and building the postgres container (fun fuct it does not work without specyfying the ports for the postgres db)

  `docker build -t dannelysbeth/quotes-postgres:1.0.0 . `
  
  `docker run -d --name quotes-database --network quotes-net -p 5432:5432 dannelysbeth/quotes-postgres:1.0.0`

### 2. Running and building the backend app (without local .jar creation)

  `docker build -t dannelysbeth/quotes-backend:1.0.0 .`
  
  `docker run -p 8080:8080 --network quotes-net --name quotes-backend  -d -e POSTGRES_USER=kodilla -e POSTGRES_PASSWORD=kodilla -e POSTGRES_DB=kodilla-quotes dannelysbeth/quotes-backend:1.0.0`

### 3. Running and creating frontend container

` docker build -t dannelysbeth/quotes-frontend:1.0.0 .`

`docker run -it --network quotes-net --name quotes-frontend -d -p 80:80 dannelysbeth/quotes-frontend:1.0.0`

### 4. Result from the browser:

<img width="2540" height="302" alt="image" src="https://github.com/user-attachments/assets/cd556920-634a-4bad-a389-8eddbde3858b" />


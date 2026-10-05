# Mission Reflection

## 1. Compose file vs. Commands

Using a docker-compose.yml file makes my work much simpler. I only need to write the setup and run it with a single command. Without the file I would have to type commands for every container and I might make mistakes. With Compose I can reuse the setup again and again. I can also share the file on GitHub so others can use it too.

## 2. What happens with an indentation error?

YAML depends on spaces to show how the file is structured. If I use a Tab of spaces Docker Compose cannot read the file and will show an error. The containers will not start until I correct the spacing. This is why I must pay attention to indentation every time I edit the file.

## 3. Why use environment variables?

We used environment variables like MYSQL_PASSWORD to set the database name, user and password without changing the image. Both containers use the values so they can connect to each other easily. In a project I would store passwords in a separate file or use a secret manager to keep them safe from being exposed.

## 4. How did it feel to deploy Nextcloud in a minutes?

Deploying Nextcloud felt quick and exciting. I felt happy and a little surprised because it was so fast. Before this I thought setting up a storage app would take hours. What surprised me the most was that one command started both the database and Nextcloud at the time.

## 5. How has my understanding of cloud computing changed since Mission 1?

In Mission 1 I thought cloud computing meant storing files on someone else’s computer. Now I see that it also includes running apps, in containers and setting up services with code. The helpful thing I learned in this mission was how to use Docker Compose to build a full app using just one file.

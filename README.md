# 🚀 Getting started with this containers

[Command Line Interface](
docker build -t jmuniz1985/app-dev:latest .
docker run -p 1337:1337 -t jmuniz1985/app-dev:latest
# upload image to dcr.io/jmuniz1985/app-dev:latest
docker push jmuniz1985/app-dev:latest 

#testar API

curl -X GET "http://34.133.130.242:1337/api/cadastros"\
 -H "Content-Type: application/json" -H "accept: application/json" -H \
 "Authorization: Bearer 92ea49a61ffca76eedbf50e90052b6d43bec3fa27bafedfd5f2f38e7b7af7c9646bdef4f3b6820eea008cec861a4c0d29b5e7f3bacaf34e37ec176913fa8df061c927e530dc2eb8d0ce449fd15ccd900334c65ccdd1806e731bfc16e0eecff44c7ca771b39ba6a9498be150a4ad369dc38ca6e43ca2895860bde39c665e83290"

docker push jmuniz1985/app-dev:latest
docker-compose build
docker-compose create 
docker-compose start
docker-compose up -d
docker push jmuniz1985/app-dev:latest

docker images
docker tag dd6675b5cfea jmuniz1985/app-devdb:latest
docker push jmuniz1985/app-devdb:latest
docker tag dd6675b5cfea  
 



### LoadBalancer is a convenient way to expose a Service to the internet 

```
npm run develop
# or
yarn develop
```

### `start`

Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/developer-docs/latest/developer-resources/cli/CLI.html#strapi-start)

```
npm run start
# or
yarn start
```

### `build`

Build your admin panel. [Learn more](https://docs.strapi.io/developer-docs/latest/developer-resources/cli/CLI.html#strapi-build)

```
npm run build
# or
yarn build
```

## ⚙️ Deployment

Strapi gives you many possible deployment options for your project. Find the one that suits you on the [deployment section of the documentation](https://docs.strapi.io/developer-docs/latest/setup-deployment-guides/deployment.html).

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://docs.strapi.io) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.

---

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>

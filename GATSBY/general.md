### LINK
    https://www.youtube.com/watch?v=Qms4k6y7OgI&list=PL4cUxeGkcC9hw1g77I35ZivVLe8k2nvjB&ab_channel=TheNetNinja

### GIT 
    https://github.com/iamshaunjp/gatsby-tutorial

### INSTALL GATSBY
    npm install -g gatsby-cli

### STARTER CODE
    https://www.gatsbyjs.com/starters/gatsbyjs/gatsby-starter-hello-world/

### ARCHITECTURE DOSSIER
    src
        components
            File.js
        pages
            file.js

### LIVE SERVER
    gatsby develop

### CREATE NEW COMPONENT
    créer nouveau fichier .js dans src/pages
    créer un react fonctional component RFC

### CREATE A LAYOUT FILE
    https://www.youtube.com/watch?v=eXzlmwFQGEc&list=PL4cUxeGkcC9hw1g77I35ZivVLe8k2nvjB&index=5&ab_channel=TheNetNinja
    - créer un fichier Layout.js dans les components
    - créer un rfc
    - dans les props de Layout ajouter { children }
    - dans return de Layout ajouter {children} à l'endroit souhaité
    - Entourer les pages de la balise <Layout></Layout>

### GLOBAL CSS
    Pour le style général du site 
    - créer folder styles dans /src
    - créer global.css dans /styles
    - import '../styles/global.css' dans Layout.js

### CSS MODULE
    pour le style de component
    - créer nomComposant.module.css dans /styles
    - import styles from '../styles/nomComposant.module.css'
    - pour appliquer une classe on utilise alors className={styles.nomDeClasse}

### AJOUTER UNE IMAGE
    - ajouter le fichier image dans /static
    - utiliser une balise normale <img src="myFile.img" />

### INSTALLER PLUGIN
    exemple avec gatsby source filesystem
    https://www.gatsbyjs.com/plugins/gatsby-source-filesystem
        - copier l'objet fournit par le site gatsby dans le fichier gatsby-config.js
    
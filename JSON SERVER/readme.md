# JSON SERVER

## INSTALL JSON SERVER ON COMPUTER
=> https://www.npmjs.com/package/json-server

## CREATE A FAKE DATA BASE
Créer un fichier monfichier.json
    Exemple de format =>
        {
            "posts": [
                {
                    "id": 1,
                    "title": "My title",
                    "body": "My content ....",
                },
                {
                    "id": 2,
                    "title": "My title",
                    "body": "My content ....",
                },
            ],
            "polls" : [
                {
                    "id": 1,
                    "question": "my question",
                    "answer1": "answer1",
                    "answer2": "answer2",
                }
            ]
        }

## START JSON SERVER AND WATCH FOR CHANGES
1-Lancer un nouveau terminal dédié à JSON SERVER
2-Run dans le terminal => json-server --watch "path of my file"/myfile.json --port 3001

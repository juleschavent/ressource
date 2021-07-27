## Install

Read / Insert https://www.youtube.com/watch?v=re3OIOr9dJI&ab_channel=PedroTech
Update / Delete https://www.youtube.com/watch?v=AohARsUlwQk&ab_channel=PedroTech

CLI

    npm install express mysql

CLI (pour tester le console.log de app.listen)

    node index.js

## Post / Insert on database

### Inside index.js

    const express = require('express')
    const app = express()
    const mysql = require('mysql') 
    const cors = require('cors')

    app.use(cors())
    app.use(express.json())

    const db = mysql.createConnection ({
        user: 'root',
        host: 'localhost',
        password: '',
        database: 'name of my db',
    })

    app.post('/create', (req, res) => {
            const name = req.body.*name of my var from frontend*
            const age = req.body.*name of my var from frontend*
            const country = req.body.*name of my var from frontend*
            etc..

            db.query('INSERT INTO people (name, age, country) VALUES (?,?,?)',          //utiliser une requête SQL
            [name, age, country], 
            (err, result) => {
                if (err) {
                    console.log(err)
                } else {
                    res.send('Values inserted')
                }
            }
        );
    })

    app.listen(3001, ()=> {
        console.log('Server is running on port 3001')
    })

### Inside App.js

import Axios from "axios"


    const App = () => {
        const [name, setName] = useState('');
        const [age, setAge] = useState(0);
        const [country, setCountry] = useState('');

        const addPeople = () => {
                //utiliser l'endpoint qui a été créer dans index.js (line-30)
            Axios.post('http://localhost:3001/create', {
                name: name, 
                age: age, 
                country: country
            }).then(() => {
                console.log('success')
            })
        }

        return (
            
        )
    }

    export default App;

## Read and display database 

### Inside index.js

    app.get('/people', (req,res) => {
        db.query('SELECT * FROM people', (err, result) => {
            if (err) {
                console.log(err)
            } else {
                res.send(result)
            }
        })
    })

### Inside component

    const App = () => {
        const [name, setName] = useState('');
        const [age, setAge] = useState(0);
        const [country, setCountry] = useState('');

        const [peopleList, setPeopleList] = useState([]);

        const getPeople = () => {
                //utiliser l'endpoint qui a été créer dans index.js (line-30)
            Axios.get('http://localhost:3001/people'.then((response) => {
                console.log(response)
                setPeopleList(response.data)
            })
        }



        return (
            
        )
    }

    export default App;


## Update database 

### Inside index.js

    app.put('/update', (req, res) => {
        const id = req.body.id
        const age =  req.body.age
        db.query('UPDATE people SET age = ? WHERE id = ?', [age, id], (err, result) => {
            if (err) {
                console.log(err)
            } else {
                res.send(result);
            }
        })
    })

### Inside component

    const App = () => {
        const [name, setName] = useState('');
        const [age, setAge] = useState(0);
        const [country, setCountry] = useState('');

        const [newAge, setNewAge] = useState(0);

        const handleChangeAge = (e) => {
            setNewAge(e.target.value)
        } 

        const updatePeopleAge = (id) => {
            Axios.put('http://localhost:3001/update', {
                age: newAge,
                id: id
            }).then((response) => {
                alert('update on bdd but not on page')
                setPeopleList(peopleList.map((val) => {
                    return val.id == id ? {
                        id: val.id, 
                        name: val.name, 
                        age: newAge,                // age est égale à newAge
                        country: country.val
                        } : val
                }))
            })
        }


        return (
            {peopleList.map((val, key) => {
                <button onClick={() => {updatePeopleAge(val.id)}}>
            })}
        )
    }

    export default App;

## Delete database 

### Inside component

    const App = () => {
        const [name, setName] = useState('');
        const [age, setAge] = useState(0);
        const [country, setCountry] = useState('');

        const deletePeople = (id) => {
            Axios.delete(`http://localhost:3001/delete/${id}`).then ((response) => {
                setPeopleList(peopleList.filter((val) => {
                    return val.id != id
                }))
            })
        }


        return (
            {peopleList.map((val, key) => {
                <button onClick={() => {deletePeople(val.id)}}>
            })}
        )
    }

    export default App;

### Inside index.js

    app.delete('/delete/:key', (req, res) => {
        const id = req.params.key
        db.query('DELETE FROM people WHERE id = ?', id, (err, result) => {
            if (err) {
                console.log(err)
            } else {
                res.send(result)
            }
        })
    })
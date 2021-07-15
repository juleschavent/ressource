# HOW TO FETCH DATA FROM API

<https://bit.ly/3r7mcue>  
La méthode peut être utilisée dans **useEffect()** pour s'exécuter au chargement de la page.

    useEffect(() => {
    fetch('uri de mon objet json, par exemple http://localhost:3001/todos')
        .then(res => {
            return res.json();
        })
        .then (data => {
            console.log(data)
        })
    }, []);

Exemple de code pour afficher les data en HTML

        return (
        <div className="todo-list">
            {todos && todos.map((todo) => (
                <div key={todo.id}>
                    <h2>{todo.id}</h2>
                    <h2>{todo.title}</h2>
                    <h2>{todo.isComplete}</h2>
                </div>
            ))}
        </div>
    );



# Projeto criado em React

### Detalhes
- Responsivo
- Consumindo API Graphql hospedada [Aqui]('https://graphql-pokemon.now.sh' "Aqui")
- Treinamento do [Scrimba](https://scrimba.com/course/greactgraphql "Scrimba")

### Screeshots

- Telas pequenas

[![Telas Pequenas](https://i.ibb.co/1s8nMYt/350px.png "Telas Pequenas")](https://i.ibb.co/1s8nMYt/350px.png "Telas Pequenas")

- Telas médias

[![Telas médias](https://i.ibb.co/fnB2Xqm/670px.png "Telas médias")](https://i.ibb.co/fnB2Xqm/670px.png "Telas médias")

- Telas grandes

[![Telas grandes](https://i.ibb.co/59Gm4Hr/maior800px.png "Telas grandes")](https://i.ibb.co/59Gm4Hr/maior800px.png "Telas grandes")

### Componente React Pokemon

```html
export function Pokemon({ pokemon }) {
	return (
		<div className="pokemon">
			<div className="pokemon__name">
				<p>{pokemon.name}</p>
			</div>
			<div className="pokemon__meta">
				<span>{pokemon.maxHP}</span>
				<span>{pokemon.maxCP}</span>
			</div>
			<div className="pokemon__image">
				<img src={pokemon.image} alt={pokemon.name} />
			</div>
			<div className="pokemon__attacks">
				{pokemon.attacks.special
					.slice(0, 3)
					.map((attack) => <span key={`${attack.name}-${attack.damage}`}>{attack.name}</span>)}
			</div>
		</div>
	);
}
```

### Query Graphql

    	query pokemons($first: Int!) {
    		pokemons(first: $first) {
    			id
    			name
    			image
    			maxHP
    			maxCP
    			attacks {
    				special {
    					name
    					damage
    				}
    			}
    		}
    	}

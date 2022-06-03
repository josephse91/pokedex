
# Pokemon Pokedex

If you're like me, the thought of being a pokemon master was a crowning achievement. 

This pokemon pokedex allows us to reference the attributes of pokemon and add pokemon within our pokedex as we please.

**Let's "catch em all"**

[Live Pokedex](https://serge-pokedex.herokuapp.com/ "Pokedex")




## Technologies Used

- Rails
- Jbuilder
- Javascript
- React
- React Router
- Redux

## Highlighted Features

**Pokemon API**

In order render pokemon in the first place, there needed to be a way to access the pokemon asynchronously in the frontend. This is done by making an API using the Rails framework. An index, create and show controller provides a response that would include all of the desired pokemon attributes/assets in JSON form (Constructed using Jbuilder)

**React Router**

To select pokemon to render, establishing a routing system was required. For each pokemon, a route was established and the store of the redux state management was accessed using ajax requests into the database.

```
render(){
    if (this.props.loading) { return <LoadingIcon />; }
    return (
      <section className="pokedex">
        <Route exact path="/" component={PokemonFormContainer} />
        <Route path="/pokemon/:pokemonId" component={PokemonDetailContainer}/>
        <ul>
          {this.props.pokemon.map((poke) => (
          <PokemonIndexItem key={poke.id} pokemon={poke}/>))
          }
        </ul>
      </section>
    )
  }
```
The portion of code above was used to access the store of the redux system and render the selected pokemon. 



## Run Locally

Clone the project

```bash
git clone https://github.com/josephse91/pokedex.git
```

Go to the project directory

Run `bundle install`
Make sure Postgres is running, then run `rails db:setup`

Install `dependencies`

`NOTE`: This app was created using npm version v14. To avoid conflict, it would be beneficial to install npm version 14. 

```bash
  npm install
```
Run the rails server

```bash
  rails s
```


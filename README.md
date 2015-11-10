## B’more on Elixir

##### Sinclair Bain


### Elixir


### Adjustments
- Functions not Methods
- Modules not Classes
- Transformation not Mutation
- Processes not Instances
- Message Sending not Method Calling
- Pattern Matching not Conditionals

#### Functions
````elixir
	
	fn -> “Hola” end
  
  fn msg -> “Hola, #{msg}!” end
  
  greet = fn msg -> “Hola, #{msg}!” end
  
  greet.(“Mundo”)
  
  “Mundo” |> greet.()

````

#### Modules
````elixir
  defmodule Greeting do
    
    def hola(msg \\ “mundo”) do
      “Hola, #{msg}!”
    end
  
  end
````

#### Transformations
- ‘copy’, ‘version’, ‘instance’
- current state ~> new state
- input, process, output

#### Processes
- Everything runs in a process
- Creating processes is similar to creating instances
- Processes are identifiable
- Processes are addressable
- Processes are cheap 

#### Message Sending
- send messages to functions running in processes
- process identifier

#### Pattern Matching (and Guard Clauses)
````elixir
defmodule Factorial do
  def of(0), do: 1
  
  def of(n) when n > 0,
  do: n * Factorial.of(n-1)
end
````

Concurrent
````
Two queues one coffee machine:   Concurrent
Two queues two coffee machines:  Parallel
````

Distribution
Nodes


OTP
GenServers
Events
Supervisors
Applications
Agents
Tasks


Tooling
- iex
- mix
- hex
- exunit
- eex


Phoenix
Web MVC
Ecto
Eex

````bash
$ mix local.hex

$ mix phoenix.new bmore_on_elixir
$ cd bmore_on_elixir
$ git init && git add . && git commit -m "Initial commit of B'more on Elixir app."

$ heroku create
$ heroku buildpacks:set https://github.com/gjaldon/phoenix-static-buildpack
$ heroku buildpacks:add --index 1 https://github.com/HashNuke/heroku-buildpack-elixir

$ git push heroku master
````




## Publish subgraph to Apollo Studio
```
rover subgraph publish paquitosofts-team@main \
  --routing-url https://flyby-locations-sub.herokuapp.com/ \
  --schema ./locations.graphql \
  --name locations
```

```
rover subgraph publish paquitosofts-team@main \
  --routing-url https://flyby-reviews-sub.herokuapp.com/ \
  --schema ./reviews.graphql \
  --name locations
```

## Run router against Apollo Studio
```
APOLLO_KEY=your-api-key \
APOLLO_GRAPH_REF=paquitosofts-team@main \
./router
```

## Compose supergraph locally
(after creating the config yaml file)
```
rover supergraph compose --config ./supergraph-config.yaml > supergraph.graphql
```

## Run the router with local supergraph
```
APOLLO_GRAPH_REF=paquitosofts-team@main \
./router --supergraph=supergraph.graphql
```
(not sure if APOLLO_GRAPH_REF in really needed in this case)

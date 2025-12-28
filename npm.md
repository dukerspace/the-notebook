# npm 

### npm pack 
- pack files

### install dev file
```
npm install -g xxx.tgz
```

### publish
```
# Update version with beta identifier
npm version 1.2.0-beta.1

# Publish with beta tag
npm publish --tag beta

# Later, when ready for stable release
npm version 1.2.0
npm publish  # publishes as 'latest' by default
```
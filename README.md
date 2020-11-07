-fork of TechMagister/couchdb.cr
- added custom method to client.cr for using externally-generated ID:  create_document_custom_id(database, object, id)
- updated for crystal 0.35.1 *
  
CouchDB client written in crystal

## Installation

Add this to your application's `shard.yml`:

```yaml
dependencies:
  couchdb:
    github: vectorselector/couchdb.cr
```

## Usage

```crystal
require "couchdb"

client = CouchDB::Client.new "http://127.0.0.1:5984"

info = client.server_info
info.couchdb # Welcome
info.version # 2.1.1
info.vendor.name # The Apache Software Foundation

```

## Development

- [x] Get server info
- [x] Create Database
- [x] Delete Database
- [x] List Databases
- [x] Get new uuid
- [x] Create Documents
- [x] Find all the documents
- [x] Find Documents with criteria
- [x] Delete Documents
- [x] Update Documents

## Contributing

1. Fork it ( https://github.com/TechMagister/couchdb/fork )
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Add some feature')
4. Push to the branch (git push origin my-new-feature)
5. Create a new Pull Request

## Contributors

- [TechMagister](https://github.com/TechMagister) Arnaud Fernandés - creator, maintainer
- [Schniz](https://github.com/Schniz) Gal Schlezinger - contributor


*among other minor API changes JSON.mapping is deprecated, instead we do the following:
```
  class FindQuery
    include JSON::Serializable
    property selector : JSON::Any
    property limit : Int64?
    property skip : Int64?
    property sort : Array(String)?
    property fields : Array(String)?
  end
```


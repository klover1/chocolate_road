# chocolate_road
  Low latency cryptocurrency data gathering and messaging in Rust

  Much akin to [CCXT](https://github.com/ccxt/ccxt), we plan to make this tool three things:
     1. Efficient
     2. Easy to use
     3. Portable across exchanges

  The point of this project isn't to make an execution engine (although a fast one would be very nice), but rather
  gather data for market analysis. We may be able to make use of [LEAN](https://github.com/QuantConnect/LEAN) instead to construct our trading strategies and
  plug it in to various exchanges. CCXT may be another option for this as well, as it already has built-in support for lots of crypto exchanges

  This project makes use of [TectonicDB](https://github.com/rickyhan/tectonicdb) to store orderbook data
  in a database efficiently. We also make use of LZMA2 to compress that data further to allow for more data storage.

  # Environment Variables
  * `AWS_ACCESS_KEY_ID`: AWS Access Key
  * `AWS_SECRET_ACCESS_KEY`: AWS Access Key Secret
  * `S3_BUCKET`: Amazon S3 Bucket to upload to. Defaults to "cuteq"
  * `S3_STORAGE_CLASS`: Amazon S3 Storage class type. Defaults to "STANDARD_IA"
  * `UPLOAD_PERIOD`: Sets the amount of time in seconds we should wait before dumping the tectonicdb database and uploading it. Defaults to 86400 seconds (one day)
  * `REDIS_AUTH`: Redis password
  * `DTF_DB_PATH`: TectonicDB Database where files are written to. Defaults to `$HOME/tectonicdb/target/release/db`

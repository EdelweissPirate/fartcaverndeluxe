# fartcaverndeluxe

## Verify Steps and Commands 

Seems some of the issue was with trying to use anchor build --verifiable and then solana-verify for other stuff... solana-verify doesn't create 'target/verifiable' so everything was getting jumbled up/missed/whatever.

Will need to do further testing with using anchor if desired.

#### Build verifiable

```
solana-verify build
```

#### Push your project to repo

```
git add -A || git commit -m "msg" || git push
```

#### Deploy

Seems to be ok to use anchor deploy here 

```
anchor deploy
```

#### Check the hashes if wanted

```
solana-verify get-executable-hash target/deploy/fartcaverndeluxe.so
```

#### Deployed hash

```
solana-verify get-program-hash -u devnet GhwiqjGuBvPJSSesTPf8YwCVhDj7UMnhj6LEaAnbZZip
```

#### Local hash example
```
480ba36938078b5581d0951e002ddbf3093c06d1f5f692041f57e884c665f54c
```

#### Deployed program hash example
```
480ba36938078b5581d0951e002ddbf3093c06d1f5f692041f57e884c665f54c
```

#### Verify and pray

Commit hash from github, library name from programs/progName/Cargo.toml

```
solana-verify verify-from-repo -u devnet --program-id GhwiqjGuBvPJSSesTPf8YwCVhDj7UMnhj6LEaAnbZZip https://github.com/EdelweissPirate/fartcaverndeluxe --commit-hash 4e04c50070745a25a4ed53857e1d05993d66c454 --library-name fartcaverndeluxe --mount-path ./
```

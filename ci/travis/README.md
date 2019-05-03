## How to ?
- Active your repository in travis-ci first
> There are two weibsites: the travis-ci.com and travis-ci.org

- create .travis.yml file


## Caveats

### #1 Encryption sensitive data

```bash
$ travis encrypt-file id_rsa --com

openssl aes-256-cbc -K $encrypted_15b8f41eeee9_key -iv $encrypted_15b8f41eeee9_iv -in .travis/id_rsa.enc -out ~/.ssh/id_rsa -d
```

If `--com` is used to encrypt data, we must deactive the other one i.e. repository settings in travis-ci.org. 

Designate `--com` or `--org` option leads to different result, this is why one site reports the building result being passed while another errored.

To deactive repository,  you need go to the `https://travis-ci.[com|org]/user/repository/settings`, turn off the `Build pushed branches` and `build pushed pull resquest`.
# Docker GitLab CE

This repository provides a base on [`sameersbn/docker-gitlab`](https://github.com/sameersbn/docker-gitlab), which we use to build
a [GitLab](https://about.gitlab.com/) image for the [Docker](https://www.docker.com/products/docker-engine) opensource
container platform.

### 📦 Requirements

The Docker & Docker Compose system requirements are Linux Ubuntu as the OS (other operating systems are supported as
well), an absolute minimum 512MB RAM (2GB recommended)

In order to install docker Ubuntu, you will need to meet the following requirements:

- OS: Linux Ubuntu
- Memory: 512MB RAM (2GB Recommended)
- Disk: Sufficient amount to run the Docker containers you wish to use
- CPU: Dependant on the applications you wish to run in the containers

### 📋 Features

- Plan
- Team Planning
- Portfolio Management
- Requirements Management
- Quality Management
- Design Management
- DORA Metrics
- Value Stream Management
- DevOps Reports
- Wiki
- Pages

### 🔧 Installation

1. Install Docker and Docker-Compose

- [Docker Install documentation](https://docs.docker.com/install/)
- [Docker-Compose Install documentation](https://docs.docker.com/compose/install/)

2. Bring up your stack by running

```shell
git clone https://github.com/trants/docker-gitlab.git \
    && cd docker-gitlab \
    && cp .env.example .env
```

3. Edit environment variable

```dotenv
# GitLab
DEBUG=false

DB_ADAPTER=postgresql
DB_HOST=gitlab-db
DB_PORT=5432
DB_USER=gitlab
DB_NAME=gitlabhq-production
DB_PASS=password
DB_EXTENSION=pg_trgm,btree_gist

REDIS_HOST=gitlab-redis
REDIS_PORT=6379

TZ=UTC
GITLAB_TIMEZONE=UTC

GITLAB_HTTPS=false
SSL_SELF_SIGNED=false

GITLAB_HOST=localhost
GITLAB_PORT=10080
GITLAB_SSH_PORT=10022
GITLAB_RELATIVE_URL_ROOT=
GITLAB_SECRETS_DB_KEY_BASE=long-and-random-alphanumeric-string
GITLAB_SECRETS_SECRET_KEY_BASE=long-and-random-alphanumeric-string
GITLAB_SECRETS_OTP_KEY_BASE=long-and-random-alphanumeric-string

GITLAB_ROOT_PASSWORD=
GITLAB_ROOT_EMAIL=

GITLAB_NOTIFY_ON_BROKEN_BUILDS=true
GITLAB_NOTIFY_PUSHER=false

GITLAB_EMAIL=notifications@example.com
GITLAB_EMAIL_REPLY_TO=noreply@example.com
GITLAB_INCOMING_EMAIL_ADDRESS=reply@example.com

GITLAB_BACKUP_SCHEDULE=daily
GITLAB_BACKUP_TIME=01:00

SMTP_ENABLED=false
SMTP_DOMAIN=www.example.com
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=mailer@example.com
SMTP_PASS=password
SMTP_STARTTLS=true
SMTP_AUTHENTICATION=login

IMAP_ENABLED=false
IMAP_HOST=imap.gmail.com
IMAP_PORT=993
IMAP_USER=mailer@example.com
IMAP_PASS=password
IMAP_SSL=true
IMAP_STARTTLS=false

OAUTH_ENABLED=false
OAUTH_AUTO_SIGN_IN_WITH_PROVIDER=
OAUTH_ALLOW_SSO=
OAUTH_BLOCK_AUTO_CREATED_USERS=true
OAUTH_AUTO_LINK_LDAP_USER=false
OAUTH_AUTO_LINK_SAML_USER=false
OAUTH_EXTERNAL_PROVIDERS=

OAUTH_CAS3_LABEL=cas3
OAUTH_CAS3_SERVER=
OAUTH_CAS3_DISABLE_SSL_VERIFICATION=false
OAUTH_CAS3_LOGIN_URL=/cas/login
OAUTH_CAS3_VALIDATE_URL=/cas/p3/serviceValidate
OAUTH_CAS3_LOGOUT_URL=/cas/logout

OAUTH_GOOGLE_API_KEY=
OAUTH_GOOGLE_APP_SECRET=
OAUTH_GOOGLE_RESTRICT_DOMAIN=

OAUTH_FACEBOOK_API_KEY=
OAUTH_FACEBOOK_APP_SECRET=

OAUTH_TWITTER_API_KEY=
OAUTH_TWITTER_APP_SECRET=

OAUTH_GITHUB_API_KEY=
OAUTH_GITHUB_APP_SECRET=
OAUTH_GITHUB_URL=
OAUTH_GITHUB_VERIFY_SSL=

OAUTH_GITLAB_API_KEY=
OAUTH_GITLAB_APP_SECRET=

OAUTH_BITBUCKET_API_KEY=
OAUTH_BITBUCKET_APP_SECRET=
OAUTH_BITBUCKET_URL=

OAUTH_SAML_ASSERTION_CONSUMER_SERVICE_URL=
OAUTH_SAML_IDP_CERT_FINGERPRINT=
OAUTH_SAML_IDP_SSO_TARGET_URL=
OAUTH_SAML_ISSUER=
OAUTH_SAML_LABEL="Our SAML Provider"
OAUTH_SAML_NAME_IDENTIFIER_FORMAT=urn:oasis:names:tc:SAML:2.0:nameid-format:transient
OAUTH_SAML_GROUPS_ATTRIBUTE=
OAUTH_SAML_EXTERNAL_GROUPS=
OAUTH_SAML_ATTRIBUTE_STATEMENTS_EMAIL=
OAUTH_SAML_ATTRIBUTE_STATEMENTS_NAME=
OAUTH_SAML_ATTRIBUTE_STATEMENTS_USERNAME=
OAUTH_SAML_ATTRIBUTE_STATEMENTS_FIRST_NAME=
OAUTH_SAML_ATTRIBUTE_STATEMENTS_LAST_NAME=

OAUTH_CROWD_SERVER_URL=
OAUTH_CROWD_APP_NAME=
OAUTH_CROWD_APP_PASSWORD=

OAUTH_AUTH0_CLIENT_ID=
OAUTH_AUTH0_CLIENT_SECRET=
OAUTH_AUTH0_DOMAIN=
OAUTH_AUTH0_SCOPE=

OAUTH_AZURE_API_KEY=
OAUTH_AZURE_API_SECRET=
OAUTH_AZURE_TENANT_ID=

# DB Backup
SCHEDULE=@weekly
BACKUP_KEEP_DAYS=7
PASSPHRASE=platonic-subdued-curvy-tweet-backroom
S3_BUCKET=my-s3-bucket
S3_REGION=us-east-1
S3_PREFIX=prefix
S3_ACCESS_KEY_ID=
S3_SECRET_ACCESS_KEY=
POSTGRES_HOST=gitlab-db
POSTGRES_USER=gitlab
POSTGRES_DATABASE=gitlabhq-production
POSTGRES_PASSWORD=password
```

4. Start GitLab CE

```shell
docker-compose up -d
```

### 📝 Usage

Reader-friendly documentation can be found [here][link-docs].

You can also find documentation on periodically backing up PostgreSQL databases to AWS S3 and restoring
from backups [here][link-docs-backup] and documentation on nginx proxy manager [here][nginx-proxy-manager].

### 📨 Message

I hope you find this useful. If you have any questions, please create an issue.

### 🔐 Security

If you discover any security related issues, please email opensource@vspc.vn instead of using the issue tracker.

### 📖 License

This software is released under the [BSD 3-Clause][link-license] License. Please see the [LICENSE](LICENSE) file
or https://vspc.vn/license for more information.

### ✨ Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <td align="center" valign="top" width="14.28%">
    <a href="https://trants.me">
      <img src="https://avatars.githubusercontent.com/u/5866677?v=4?s=100" width="100px;" alt="Son Tran Thanh" />
      <br />
      <sub>
        <b>Son Tran Thanh</b>
      </sub>
    </a>
    <br />
    <a href="https://github.com/trants/docker-aws-backup/commits?author=trants" title="Code">💻</a>
    <a href="https://github.com/trants/docker-aws-backup/commits?author=trants" title="Documentation">📝</a>
  </td>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://allcontributors.org) specification.
Contributions of any kind welcome!

[link-docs]: https://github.com/sameersbn/docker-gitlab
[link-docs-backup]: https://github.com/trants/postgres-backup
[nginx-proxy-manager]: https://github.com/trants/npm
[link-license]: https://opensource.org/license/bsd-3-clause

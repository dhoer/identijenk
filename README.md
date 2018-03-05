# identijenk

Updated version of `identijenk` mentioned in _Chapter 8 - Continuous Integration and Testing with Docker_ of [Using Docker](https://www.amazon.com/Using-Docker-Developing-Deploying-Containers/dp/1491915765/ref=sr_1_1?ie=UTF8&qid=1520226136&sr=8-1&keywords=using-docker) by Adrian Mouat.

Demonstrates the use of [Declaritive Multibranch Pipelines](https://jenkins.io/doc/book/pipeline/syntax/#declarative-pipeline) in Jenkins 2.x for identidock.

## Setup Jenkins Server

1. Build and start the jenkins image:

        docker-compose up --build -d

1. Get the initial password:

        cat .jenkins_home/secrets/initialAdminPassword

1. Open http://localhost:8080/ and paste in initial password

1. Install suggested plugins

1. Get a cup  of coffee or tea

1. Create First Admin User

1. Create New Item -> Multibranch Pipeline called `indentidock`

1. Add git source `git@github.com:dhoer/identidock.git`

1. Create and use credentials: Kind -> SSH Username with private key (allows readonly access to dhoer/identidock.git)

    1. Id:

            identidock

    1. Private key:

            -----BEGIN RSA PRIVATE KEY-----
            MIIEowIBAAKCAQEAsR2UWuINSLZd1D2gY36+pFBGDZmxKvYiC/AQ5NnFl/bCrMLO
            3yR9CU6Cme6Tp0+2uUx1pjCmR5+yzM5IxiT/+M7AhWtKf9ktg2FA5jfNbzraBVee
            Pjb9aiJequkFZizFIFOpv/Z+pylVmiEW0IgFxkzeadmIvtpqr12/kwMiMa8KtGSp
            M+VTZ0M5DQjmZZaiUlJ+5VVkp/8r0hSj8m6G64N/x2xXi3l1BnqMcHjJLexhig3U
            h31CfCTU01oTrHF8N5ZZOTN7Bc5yxCpUaF+3ZXXK5kab17oT+mCShiElcTMnsl6n
            p/O16t4msWcwok8GCrl77ZKhQ8PA/etyJ5Vn3QIDAQABAoIBAG/PGIR3B6PLXFhL
            vyCQNpFMC60yROG2F7ApkMCnqVFReXvOTwIW6sghQ9kg/x0z+Unotqx/MbktW5Zm
            8xIC8YSEII0ZOiKTW2QA1ROATrPVFyUgNslXtYp2wARsrffec2MA7bw9Q58LPPrb
            wKdL9zlD9XQk22qAP7ENIY8Q/1kU9YFpK8HGRuBkPJDuZNdxU6DSpLIqfIn8kJKO
            3GZBElvKJfmuEKC7qLXvpSAJ6EJ2kDpzcMOYHUih2SqiGPaLfv+rXpILuPKf4Lgu
            SisGdBwYH+Q331KC5ZEJ++4PL/vcaz5JRM/2bngHPfxJHJ1GQ90h/GzSR/NsOcvl
            EwKfmQECgYEA57+2KZ0hmIZryBr2QbLBQ054jwUAuvQAqIp1XQC+V3zZOwqKlble
            TQPexMKsDlKLtv1ES2PPR3bWZwVW8k14Zsu4V3lwvgYtD5s8rsKrqFr9EWC/ooGg
            zbTGMlqLXg9eUX3fn5Km2nUfLMENTEv9+xIvK9ayJ9Cn2nAK/csm+80CgYEAw6ZN
            o+4S2uO+MG/p3g9jklXcuXfvlnGhPCzrV/DvxFRHAYPa77EcdYuacwHvOyOobXVG
            m4kN71Vn9ftiq/9hsl9zyUh++eV2pXexNxnbK7YrCAFIra6xl4eqlOPDVTYksGsR
            r+M7yevF6z1bchirLdlLA8oOwQs6T+TVi81arFECgYEAqSixscxlQm0T7Vto1unA
            0f1MWLDBKLWEaYGvSzSIu1mBQuxd3g4RfEvP5nVmm4m7O9XAbPssyLBArbAjF/he
            Y0Jei1M0bTAa4iJg9/tWyyunP3EMUHUoSB6k8QpQYlb7dKZZfaPRMPJ+z+8WYtOx
            Tvul/OzY2+EdNH/GNhx8lx0CgYA1jQVfQ0Ch7QgXleo7P5cPbLT3ht5rHTr2j4zz
            Cx11bWPqBD8esCmL+uQRaowiccYd/6WN2NuZkJTd/SqqzUHeYsX8Z/1pROdOrw4w
            eMFGm5v3mvJbp58wTI/iJN1IK4OrTgMPU3D/+aq4kpi/CAWCjSE9LkcPi5UwXQAe
            Pdz9oQKBgBwS+7wOJxasgEaQzyLLxbN1VKRVsLXH3XVjDKOIBS52rPChmRqW66Sx
            D9bK+0sHHfYBICMHqwxSn89OPzoyFtxG24TJ5+PbaGrMJsEspap4OLj01b+STzhg
            eofUSODT/qHRjQKYOZIQgT8i4B4uo2RHRpc5Yp6oEXkxmK0An6KC
            -----END RSA PRIVATE KEY-----

You should now see the master branch of identidock building.

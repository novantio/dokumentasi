# Jenkins

## documentation
for automated build/compile exe , pull/push into git, can customed 

## command
to run 
```
java -jar jenkins.war --httpPort=8080
```


## jenkin cli
url jenkin cli
```
http://your-jenkins-url:port/cli
```

create api token
```
JENKINS_URL:PORT/user/YOUR_USER/configure
```

command to run
```
java -jar jenkins-cli.jar -auth admin:12780e8a3daea289dnov38f059ddd3b333  -s http://localhost:8010/ build "build-production" 
```

## sample pipeline script for windows
```
pipeline {
    agent any
    stages {
        stage('downloading git') {
            steps {
                dir("E:\\location\\production"){
                    git branch: 'master',
                        credentialsId: '67c8a561-c2e6-50cf-96b2-412aef39f0d1',
                        url: 'http://gitserver.com:3000/location/development.git'
                }
            }
        }
        stage('build') {
            steps {
                dir("E:\\location\\production"){
                    bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\MSBuild\\15.0\\Bin\\MSBuild.exe" production.sln /p:Configuration=Debug'
                }
            }
        }
        
        stage('force push') {
            steps {
                dir("E:\\location\\production"){
                    bat 'git remote remove origin'
                    bat 'git remote add origin http://gitserver.com:3000/location/production.git'
                    bat 'git push -u http://user:password@gitserver.com:3000/location/production.git master --force'
                    
                }
            }
        }
        
        stage('done') {
            steps {
                dir("E:\\location\\production"){
                    bat 'echo "done"'
                }
            }
        }
    }
}

```

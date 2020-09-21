# HLavalink

간단히 말해 **Lavalink** 를 **Heroku** 에서 실행합니다.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/F4stZ4p/HLavalink)

Lavalink는 [이곳](https://github.com/Cog-Creators/Lavalink-Jars/releases)에서 다운받습니다.

## 사용법:

### 쉬운 설치
- [x] "Deploy to Heroku" 버튼을 클릭하고 설치를 진행하세요.

### 조금 더 어려운 방법
- [x] Heroku 에서 애플리케이션을 만듭니다.
- [x] buildpacks 에 Java 를 추가합니다.
- [x] 이 레포를 포크하고 Heroku 에 deploy 하세요.

# 중요한 메모:
- [x] 만약 이것이 켜진상태로 유지하기를 원하신다면, UptimeRobot service 계정을 만들고 5분마다 앱에 HTTP 요청을 해야 하는 것이 필요합니다. 예를 들어, 만약 당신의 앱의 이름이 `test-lavalink` 라 하면 HTTP 요청을 `http://test-lavalink.herokuapp.com` 로 설정하세요.
- [x] config 파일을 수정하는 것을 잊지 마세요. (application.yml)
- [x] 당신의 비밀번호를 설정하는 것을 잊지 마세요 (`PASSWORD` 환경 변수)

# 장점
- [x] **최신** 릴리즈의 Lavalink 를 재시작할 때마다 사용할 수 있습니다.
- [x] 완전 무료!
- [x] ***3 번의 클릭***으로 시작하는 HLavalink 생활

# 연결
- [x] Lavalink 의 포트는 언제나 80 입니다, application.yml 에서 포트를 수정하지 마세요!
- [x] 비밀번호는 `PASSWORD` 환경변수입니다, 만약 이 변수가 존재하지 않는다면, 그것은 `youshallnotpass` 입니다.

# 예제

## Python
### discord.py

- [x] **Wavelink** | **[Repo Link](https://github.com/EvieePy/Wavelink)**
```python
async def initiate_nodes(self):
    nodes = {"MAIN": 
        {
            "host": "test-lavalink.herokuapp.com",
            "port": 80,
            "rest_url": "http://test-lavalink.herokuapp.com",
            "password": "youshallnotpass",
            "identifier": "MAIN",
            "region": "europe"
        }
    }

    for n in nodes.values():
        # ...
```
- [x] **Lavalink.py** | **[Repo Link](https://github.com/Devoxin/Lavalink.py)**
```python
async def initiate_nodes(self):
    self.bot.lavalink = lavalink.Client(
        self.bot.user.id
    )
    
    self.bot.lavalink.add_node(
        "test-lavalink.herokuapp.com", 
        80, 
        "youshallnotpass", 
        "eu", 
        "default-node"
    )  # 호스트, 포트, 비밀번호, 리전, 이름
    # ...
```

# 고급
### 만약 당신이 Heroku 기본 Java 옵션이 맘에 들지 않는 경우:
- [x] 당신은 `ADDITIONAL_JAVA_OPTIONS` 변수로 커스텀 Java flags 를 설정할 수 있습니다. 그것은 기본 config 을 **무시합니다**. 만약 당신이 **무엇을 하고 있는지 모르시고 있다면** 앞의 방법을 사용하지 마세요.

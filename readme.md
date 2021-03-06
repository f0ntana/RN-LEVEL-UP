# React Native
>### Saindo do Level 1


#### Criando o Projeto

Se você vai criar um projeto, aconselho ler esse tópico:
 - https://reactnative.dev/docs/environment-setup 

Eu particularmente, para uma experiencia REAL, aconselho o caminho "React Native CLI Quickstart"

em Resumo:

* para projetos sem firebase: 
```
npx @react-native-community/cli init AwesomeProject --version="^0.61.0"

```

* para projetos sem firebase e com typescript:  
```
npx @react-native-community/cli init AwesomeTSProject  --version="^0.61.0"
--template=react-native-template-typescript
```

* para projetos com firebase:
(https://invertase.io/oss/react-native-firebase/quick-start/new-project)

```
npx @react-native-community/cli init --template=@react-native-firebase/template AwesomeFirebaseProject --version="^0.61.0"

```


> Na pasta CriandoProjeto, tem um exemplo criado com cada um deles :D

---
### Ferramentas de Debug

Pra debug de rede eu uso o reactotron:

https://github.com/infinitered/reactotron/blob/master/docs/quick-start-react-native.md


```js
import Reactotron from 'reactotron-react-native'
import AsyncStorage from '@react-native-community/async-storage';

Reactotron
  .setAsyncStorageHandler(AsyncStorage) 
  .configure()  
  .useReactNative()  
  .connect()  
  
```



---
### Libs de UI


#### React-Native-Paper

Experiencia boa pra material ui 

https://callstack.github.io/react-native-paper/

```
yarn add react-native-paper react-native-vector-icons
react-native link react-native-vector-icons
```
getting started em -> https://callstack.github.io/react-native-paper/getting- started.html

#### React-Native-Elements

Experiencia de UI mais agnostica

https://react-native-elements.github.io/react-native-elements

```
yarn add react-native-elements react-native-vector-icons
react-native link react-native-vector-icons
```
getting started em -> https://callstack.github.io/react-native-paper/getting-started.html



### HTTP ?!


#### Axios ! 

`yarn add axios`

para requisições!!!!

para mais -> https://github.com/axios/axios


```js
 const buscar = useCallback(async () => {

    const { data } = await axios.get(`https://api.github.com/users/castrolol`)

    setUser(data)

  }, [username])

```


### Chatzinho!!

`yarn add react-native-gifted-chat`

https://gifted.chat
https://github.com/FaridSafi/react-native-gifted-chat

```js

import React, { useState } from 'react';
import { GiftedChat } from 'react-native-gifted-chat'
import { useListVals } from 'react-firebase-hooks/database';
import database from '@react-native-firebase/database'


export default function App() {
  const [messages] = useListVals(database().ref("messages"));
 
  return (
    <GiftedChat
      messages={messages}
      onSend={messages => {
        database().ref("messages").push(messages[0])
      }}
      user={{
        _id: 1,
      }}
    />

  )
}
```




### Mais coisinhas

* Jest - Testes!
* Detox (https://github.com/wix/Detox) - e2e
* Awesome React Native (https://github.com/jondot/awesome-react-native) -  conjunto de mtas  coisas tops em RN
* Awesome React NAtive UI (https://github.com/madhavanmalolan/awesome-reactnative-ui) - conjunto de coisas top em UI!




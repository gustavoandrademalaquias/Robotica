# codigo para entender e desenhar a lógica do robô

### Header:
  - Mapa (irei definir tudo isso em lua, não em python, fds)
```lua
Mapa = {} :: {
  {int, int, int}: { --[x,y,z= { feixes lançados nesse ponto } 
    { 
      DistanceFromStartingPoint: {int, int | 0, int},
      ObjectColor: string
    }
  }
}
```

### Functions
Primeira função que o robo precisará será a de detectar o ambiente (detectar_ambiente), essa função vai fazer o seguinte:
  - Rodar o robô, para cada grau que ele virar, irá enviar um sinal (até o momento, infravermelho) e detectar as seguintes propriedades:
    - distancia percorrida,
    - cor do objeto detectado
    - posição atual do robô no plano, até o momento xyz ou xz (0, 0, 0 será o início do circuito, ou seja, o meio do mapa, posteriormente mostrado no display led).

    Após isso, salvar na variável Mapa as propriedades para esse feixe.
    - Insert(mapa[posicao_robo], [DistanceFromStartingPoint = 0, ObjectColor = 0]
    - Código equivalente, em python
```py
robot_position = [0, 0, 0]
distancia_percorrida, cor = enviar_feixe() # unknown function, to define

distancia_calculada = [ 
  robot_position[0] + distancia_percorrida[0],  
  robot_position[1] + distancia_percorrida[1],  
  robot_position[2] + distancia_percorrida[2],  
] # (x, y, z) althought i dont think we'll use Y, maybe we even can't
```

- Led display


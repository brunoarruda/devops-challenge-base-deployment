# DevOps Challenge (Deployment)

Repositório para controle do deployment no ambiente de laboratório relacionado ao Challenge

## TODO

- [x] Ingress argoCD
- [x] Bombardier
- [x] Pseudo Java Backend Manifests
- [x] MySQL
- [ ] Usar ApplicationSet para gerar Applications

## Sobre o Repositório

O repositório possui a seguinte estrutura:

```text
├── applications
│   ├── argocd
│   │   └── <deployment files>
│   ├── bombardier
│   │   └── <deployment files>
│   ├── java-backend
│   │   └── <deployment files>
│   └── mysql
│       └── <deployment files>
├── bootstrap
│   └── <deployment files>
└── README.md
```

O ArgoCD monitora esse repositório, especificamente a pasta `bootstrap`. A partir dela, ele identifica applications que apontam para outras pastas dentro do repositório onde há a configuração para fazer o deployment. Esse é um padrão conhecido como App of Apps, e o objetivo inicial era utilizar um ApplicationSet para montar os Applications que acabaram sendo adicionados à pasta `bootstrap`, entretanto o ApplicationSet não funcionou como esperado, portanto cada deploy configurado na pasta `applications` também precisa ter um Application correspondente na pasta `bootstrap`.

FORMAT: 1A
HOST: https://api.imocorretor.com.br/sites/v1

# API do imoCorretor (v1)

## Sobre esta API

A Nativa Sistemas, empresa de tecnologia e desenvolvedora do Sistema imoGestão,
está disponibilizando a seus clientes a possibilidade de integrar seus imóveis,
lançamentos, contatos entre outros recursos diretamente ao sistema.

## Autenticação

O uso desta API requer uma chave de segurança que vai garantir a segurança de seus
dados. Esta chave deverá ser obtida junto ao nosso canal de Suporte no e-mail
suporte@nativasistemas.com.br

## Segurança

Apesar da API permitir solicitações por GET, recomendamos que não utilize
chamadas através de "client-side" para manter o sigilo de suas informações,
bem como não expor a sua chave de acesso.

# Empresa [/empresa.json?api={api}]

Dados da empresa e ajustes relacionados a customização do site

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)

+ Response 200 (application/json)

        {
            "id": "000",
            "nome": "Nome da Imobiliária",
            "creci": "Número do CRECI",
            "horario": "Horário de atendimento",
            "endereco": "Endereço da imobiliária",
            "telefones": {
                "telefone_principal": "Telefone Principal",
                "telefone_segundario": "Telefone Secundário",
                "telefone_movel": "Telefone móvel ou de plantão",
                "telefone_whatsapp": "Telefone de plantão no Whatsapp"
            },
            "email": {
                "email_comercial": "email@email.com",
                "email_vendas": "email@email.com",
                "email_locacao": "email@email.com",
                "email_geral": "email@email.com",
                "email_financeiro": "email@email.com"
            },
            "site": {
                "centraldocliente": "https://sistema.imogestao.com.br/cliente/?c=",
                "versao_site": "v1",
                "cor_principal": "#000",
                "cor_texto": "#000",
                "cor_fundo": "#000",
                "cor_alternativo_texto": "#000",
                "cor_alternativo_fundo": "#000",
                "facebook": "https://facebook.com/url_empresa/",
                "instagram": "https://instagram.com/url_empresa",
                "youtube": "https://youtube.com/url_empresa",
                "twitter": "https://twitter.com/url_empresa",
                "seo_keywords": "palavras chaves da empresa",
                "seo_description": "Uma breve descrição da empresa",
                "seo_script": "",
                "texto_livre": "Texto livre para incluir no site",
                "sobre_texto": "Texto sobre a empresa",
                "sobre_imagens": [
                    "http://sistema.imogestao.com.br/imagem.jpg"
                ],
                "logo": "http://sistema.imogestao.com.br/imagem.jpg",
                "banners": [
                    {
                        "imagem": "http://sistema.imogestao.com.br/imagem.jpg",
                        "link": "http://sistema.imogestao.com.br/",
                    }, {
                        "imagem": "http://sistema.imogestao.com.br/imagem.jpg",
                        "link": "http://sistema.imogestao.com.br/",
                    },
                ]
            },
            "simuladores": {
                "simulador_caixa": "1",
                "simulador_caixa_link": "http://www8.caixa.gov.br",
                "simulador_bancobrasil": "1",
                "simulador_bancobrasil_link": "https://www42.bb.com.br/portalbb/cim/creditoimobiliario/simular,802,2250,2250.bbx",
                "simulador_bradesco": "1",
                "simulador_bradesco_link": "https://banco.bradesco/html/classic/produtos-servicos/emprestimo-e-financiamento/encontre-seu-credito/simuladores-imoveis.shtm",
                "simulador_itau": "1",
                "simulador_itau_link": "https://banco.bradesco/html/classic/produtos-servicos/emprestimo-e-financiamento/encontre-seu-credito/simuladores-imoveis.shtm"
            }
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Filtros [/filtros.json?api={api}&pretensao={pretensao}&tipo={tipo}&cidade={cidade}]

Prepara os campos de busca com informações de filtros

## Obtendo dados [GET]

+ Parameters

    + api (string) ... Chave de acesso (obrigatório)
    + pretensao (string) ... Filtra os campos com base na pretensão informada
    + tipo (number) ... Filtra os campos com base no tipo informado
    + cidade (number) ... Filtra os campos e relaciona os bairros com base na cidade informada

+ Response 200 (application/json)

        {
            "tipos": [
                {
                    "id": "1",
                    "label": "Apartamento"
                }, {
                    "id": "6",
                    "label": "Fazenda"
                }, {
                    "id": "9",
                    "label": "Kitnet"
                }, {
                    "id": "12",
                    "label": "Prédio Residencial"
                }, {
                    "id": "13",
                    "label": "Sala Comercial"
                }, {
                    "id": "15",
                    "label": "Cobertura"
                }, {
                    "id": "16",
                    "label": "Sobrado"
                }, {
                    "id": "23",
                    "label": "Casa"
                }, {
                    "id": "25",
                    "label": "Ponto Comercial"
                }
            ],
            "pretensao": [
                {
                    "id": "alugar",
                    "label": "Alugar"
                }, {
                    "id": "comprar",
                    "label": "Comprar"
                }
            ],
            "cidade": [
                {
                    "id": "4201406",
                    "label": "Araranguá"
                }, {
                    "id": "4202008",
                    "label": "Balneário Camboriú"
                }, {
                    "id": "4202404",
                    "label": "Blumenau"
                }, {
                    "id": "4209409",
                    "label": "Laguna"
                }, {
                    "id": "4214805",
                    "label": "Rio do Sul"
                }, {
                    "id": "4217808",
                    "label": "Taió"
                }, {
                    "id": "4218905",
                    "label": "Urubici"
                }, {
                    "id": "4219507",
                    "label": "Xanxerê"
                }
            ],
            "bairros": [
                {
                    "id": "30552",
                    "label": "Centro"
                }, {
                    "id": "30555",
                    "label": "Garcia"
                }, {
                    "id": "30563",
                    "label": "Passo Manso"
                }, {
                    "id": "30565",
                    "label": "Ponta Aguda"
                }, {
                    "id": "30573",
                    "label": "Velha"
                }, {
                    "id": "30579",
                    "label": "Água Verde"
                }, {
                    "id": "36168",
                    "label": "Fortaleza Alta"
                }
            ],
            "dormitorios": [
                {
                    "id": "0"
                }, {
                    "id": "1"
                }, {
                    "id": "2"
                }, {
                    "id": "3"
                }, {
                    "id": "4"
                }
            ],
            "garagens": [
                {
                    "id": "0"
                }, {
                    "id": "1"
                }, {
                    "id": "2"
                }
            ],
            "banheiros": [
                {
                    "id": "0"
                }, {
                    "id": "1"
                }, {
                    "id": "2"
                }
            ],
            "suites": [
                {
                    "id": "0"
                }, {
                    "id": "1"
                }, {
                    "id": "2"
                }
            ],
            "mobiliado": [
                {
                    "id": 0,
                    "label": "Sem Mobilia"
                }, {
                    "id": 1,
                    "label": "Mobiliado"
                }, {
                    "id": 2,
                    "label": "Semi-mobiliado"
                }
            ]
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Imóveis [/imoveis.json?api={api}&tipo={tipo}&venda={venda}&venda_valor_min={venda_valor_min}&venda_valor_max={venda_valor_max}&locacao={locacao}&locacao_valor_min={locacao_valor_min}&locacao_valor_max={locacao_valor_max}&cidade={cidade}&bairro={bairro}&bairros={bairros}&dormitorio={dormitorio}&suite={suite}&banheiro={banheiro}&garagem={garagem}&mobiliado={mobiliado}&destaque={destaque}&edificio={edificio}&limite={limite}&ordem={ordem}&pagina={pagina}]

Relaciona todos os imóveis da imobiliária com a possibilidade de realizar filtros, todos os campos podem ser obtidos com base nas informações de `Filtros`.

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + tipo (number) - Tipo dos imóveis (obtenha os códigos em `Filtros`)
    + venda (number) - Informe "1" para obter imóveis de venda
    + venda_valor_min (number) - Valor mínimo de venda (obrigatório informar `venda`)
    + venda_valor_max (number) - Valor máximo de venda (obrigatório informar `venda`)
    + locacao (number) - Informe "1" para obter imóveis de locação
    + locacao_valor_min (number) - Valor mínimo de locação (obrigatório informar `locacao`)
    + locacao_valor_max (number) - Valor máximo de locação (obrigatório informar `locacao`)
    + cidade (number) - Cidade dos imóveis (obtenha os códigos em `Filtros`)
    + bairro (number) - Bairro dos imóveis (obrigatório informar a cidade, obtenha os código em `Filtros`)
    + bairros (number) - Igual `bairro` porém com seleção multipla separadas por ',' ex: 123,234,345
    + dormitorio (number) - Número de dormitórios dos imóveis
    + suite (number) - Número de suítes dos imóveis
    + banheiro (number) - Número de banheiros dos imóveis
    + garagem (number) - Número de garagens dos imóveis
    + mobiliado (number) - Opção de Sem/Com/Semi Mobilia(do) dos imóveis (obtenha os códigos em `Filtros`)
    + destaque (number) - Informe "1" para listar apenas imóveis em destaque
    + edificio (number) - Filtra unidades de um lançamento (ver lançamentos) usar código 'edificio'
    + limite (number) - Limite de imóveis por resultado, por padrão, o limite máximo é de `24` imóveis
    + ordem (number) - Ordenação dos imóveis (1 = Preço (obrigatório informar `venda` ou `locacao`), 2 = Cidade, 3 = Bairro, 4 = Área útil)
    + pagina (number) - Paginação dos imóveis, se deseja apresetar a terceira página, será necessário aplicar `(24 x 2)` o que representa `48` imóveis em diante

+ Response 200 (application/json)

        {
            "resultados": 1,
            "imoveis": [
                {
                    "id": "123",
                    "referencia": "3",
                    "tipo": "Terreno",
                    "pretensao": {
                        "venda": "1",
                        "locacao": "1",
                    },
                    "finalidades": {
                        "residencial": "1",
                        "comercial": "1",
                        "rural": "0"
                    },
                    "localizacao": {
                        "estado": "SC",
                        "cidade": "Blumenau",
                        "bairro": "Centro",
                    },
                    "edificio_nome": null,
                    "valores": {
                        "valor_venda": "2500000",
                        "valor_locacao": "0",
                        "valor_iptu": "0",
                        "valor_condominio": "0"
                    },
                    "dormitorios": "0",
                    "suites": "0",
                    "banheiros": "0",
                    "salas": "0",
                    "garagens": "0",
                    "area_util": "100",
                    "area_total": "120",
                    "area_terreno": "129",
                    "texto_curto": "Terreno escriturado no Bairro Fidélis, com 7.061,82 m² contendo galpão estrutural com área de 1.450,00 m².",
                    "texto_longo": "Terreno escriturado no Bairro Fidélis, com área total de 7.061,82 m², fazendo frente em 59,78 metros, fundos em 60,00 metros, lado direito em 141,30 metros e lado esquerdo em 149,30 metros. Possui um galpão estrutural com área de 1450,00 m².",
                    "fotos": [
                        {
                            "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "descricao": "Fachada"
                        }, {
                            "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "descricao": "Fachada"
                        }, {
                            "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                            "descricao": "Fachada"
                        }
                    ]
                }
            ]
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Imóvel [/imovel.json?api={api}&id={id}&referencia={referencia}]

Apresenta uma ficha completa do imóvel. Necessário informar o ID / Referencia 

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + id (number) - Código do imóvel (obtenha os códigos em `Imóveis`)
    + referencia (number) - Código do referencia do imóvel (obtenha os códigos em `Imóveis`)

+ Response 200 (application/json)

        {
            "id": "123",
            "referencia": "3",
            "tipo": "Terreno",
            "finalidades": {
                "residencial": "1",
                "comercial": "1",
                "rural": "0"
            },
            "localizacao": {
                "estado": "SC",
                "cidade": "Blumenau",
                "bairro": "Centro",
                "latitude": "-26.9249002",
                "longitude": "-49.0611365"
            },
            "edificio_nome": null,
            "valores": {
                "valor_venda": "2500000",
                "valor_locacao": "0",
                "valor_iptu": "0",
                "valor_condominio": "0"
            },
            "dormitorios": "0",
            "suites": "0",
            "banheiros": "0",
            "salas": "0",
            "garagens": "0",
            "area_util": "100",
            "area_total": "120.12",
            "area_terreno": "129.12",
            "texto_curto": "Terreno escriturado  no Bairro Fidélis, com 7.061,82 m² contendo galpão estrutural com área de 1.450,00 m².",
            "texto_longo": "Terreno escriturado no Bairro Fidélis, com área total de 7.061,82 m², fazendo frente em 59,78 metros, fundos em 60,00 metros, lado direito em 141,30 metros e lado esquerdo em 149,30 metros. Possui um galpão estrutural com área de 1450,00 m².",
            "fotos": [
                {
                    "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "descricao": "Fachada"
                }, {
                    "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "descricao": "Fachada"
                }, {
                    "pequena": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "media": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "grande": "http://www.imogestao.com.br/fotos/xxx/xxx.jpg",
                    "descricao": "Fachada"
                }
            ]
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Mapa [/mapa.png?api={api}&id={id}&referencia={referencia}]

Apresenta mapa em forma de imagem com um ponto exato ou aproximado do imóvel. Necessário informar o ID / Referencia 

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + id (number) - Código do imóvel (obtenha os códigos em `Imóveis`)
    + referencia (number) - Código do referencia do imóvel (obtenha os códigos em `Imóveis`)

+ Response 200 (image/png)

+ Response 404 (text/plain)

        Chave de acesso inválida ou não informada

# Relacionados [/relacionados.json?api={api}&id={id}&referencia={referencia}&venda={venda}&locacao={locacao}]

Apresenta uma relação de imóveis próximo e/ou relacionados ao imóvel informado

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + id (number) - Código do imóvel (obtenha os códigos em `Imóveis`)
    + referencia (number) - Código do referencia do imóvel (obtenha os códigos em `Imóveis`)
    + venda (bool) - Mostra apenas imóveis de venda
    + locacao (bool) - Mostra apenas imóveis de locação

+ Response 200 (application/json)

        {
            
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Lançamentos [/lancamentos.json?api={api}]

Relação de Lançamentos / Empreendimentos (em testes)

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "nome": "Nome do Lançamento",
                "detalhes_lancamento": "Detalhes em <strong>HTML</strong> do lançamento",
                "detalhes_apartameto": "Detalhes em <strong>HTML</strong> do apartamento"
            }, {
                "id": "2",
                "nome": "Nome do Lançamento",
                "detalhes_lancamento": "Detalhes em <strong>HTML</strong> do lançamento",
                "detalhes_apartameto": "Detalhes em <strong>HTML</strong> do apartamento"
            }
        ]

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Lançamento [/lancamento.json?api={api}&id={id}]

Detalhes do Lançamento / Empreendimento (em testes)

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + id (number) - ID do empreendimento (obter em empreendimentos)

+ Response 200 (application/json)

        {
        }


+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Newsletter [/newsletter.json?api={api}]

Registra emails de newsletter no sistema.

## Encaminhando os dados [POST]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    
+ Attributes (object)

    + email (string) - Email do cliente (obrigatório se não houver telefone)

+ Request (application/json)

+ Response 200 (application/json)

        {
            "ok": "Obrigado! Seu cadastro ao newsletter foi recebido com sucesso."
        }

+ Response 206 (application/json)

        {
            "erro": {
                "Erro interno, nenhuma informação foi encaminhada",
                "Email não informado",
            }
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Contato [/contato.json?api={api}]

Registra um atendimento no sistema.

## Encaminhando os dados [POST]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    
+ Attributes (object)

    + nome (string) - Nome do cliente (mínimo de 3 letras)
    + email (string) - Email do cliente (obrigatório se não houver telefone)
    + fone (string) - Telefone do cliente (obrigatório se não houver email)
    + texto (string) - Mensagem do cliente (obrigatório se não houver imóvel informado)
    + imovel (number) - `id` do imóvel (obter em `imóveis` ou `imóvel`)

+ Request (application/json)

+ Response 200 (application/json)

        {
            "ok": "Obrigado! Sua mensagem foi recebida com sucesso."
        }

+ Response 206 (application/json)

        {
            "erro": {
                "Erro interno, nenhuma informação foi encaminhada",
                "Email ou Telefone não informado",
            }
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Equipe [/equipe.json?api={api}]

Relaciona os usuários do sistema

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)

+ Response 200 (application/json)

        {
          "Diretoria": [
            {
              "id": "0",
              "nome": "Usuário Sobrenome",
              "apelido": "Usuárop",
              "cargo": "Treinamentos",
              "creci": "00000",
              "email": "usuario@dominio.com.br",
              "celular": "(00) 0000-0000",
              "foto": "https://sistema.imogestao.com.br/fotos/xxx/xxx.jpg",
              "livre": "Um pouco sobre mim..."
            }
          ],
          "Corretores": [
            {
              "id": "0",
              "nome": "Usuário Sobrenome",
              "apelido": "Usuárop",
              "cargo": "Administrador",
              "creci": "00000",
              "email": "usuario@dominio.com.br",
              "celular": "(00) 0000-0000",
              "foto": "https://sistema.imogestao.com.br/fotos/xxx/xxx.jpg",
              "livre": "Um pouco sobre mim..."
            },
            {
              "id": "0",
              "nome": "Usuário Sobrenome",
              "apelido": "Usuárop",
              "cargo": "Administrador",
              "creci": "00000",
              "email": "usuario@dominio.com.br",
              "celular": "(00) 0000-0000",
              "foto": "https://sistema.imogestao.com.br/fotos/xxx/xxx.jpg",
              "livre": "Um pouco sobre mim..."
            }
          ],
          "Financeiro": [
            {
              "id": "0",
              "nome": "Usuário Sobrenome",
              "apelido": "Usuárop",
              "cargo": "Representante",
              "creci": "00000",
              "email": "usuario@dominio.com.br",
              "celular": "(00) 0000-0000",
              "foto": "https://sistema.imogestao.com.br/fotos/xxx/xxx.jpg",
              "livre": "Um pouco sobre mim..."
            }
          ]
        }


+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Blogs [/blogs.json?api={api}&destaque={destaque}&limite={limite}&pagina={pagina}]

Relação de Blogs / Notícias (em testes)

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + destaque (bool) - Mostrar apenas destaques
    + limite (number) - Limite de blogs por resultado, por padrão, o limite máximo é de `24` blogs
    + pagina (number) - Paginação dos blogs, se deseja apresetar a terceira página, será necessário aplicar `(24 x 2)` o que representa `48` blogs em diante

+ Response 200 (application/json)

        [
            {
            "id": "10",
                "codigoempresa": "310",
                "codigousuario": "44",
                "ativo": "1",
                "destaque": "0",
                "publicado": "1",
                "slug": "teste",
                "titulo": "Teste",
                "resumo": "teste",
                "conteudo": "<p>teste</p>",
                "tags": null,
                "autor": "teste",
                "criadoem": "2017-09-29 17:38:58",
                "publicarem": "2018-05-09",
                "exibicao": "0"
            }
        ]

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

# Blog [/blog.json?api={api}&id={id}&slug={slug}]

Mostra Blog / Notícia (em testes)

## Obtendo dados [GET]

+ Parameters

    + api (string) - Chave de acesso (obrigatório)
    + id (number) - ID único do Blog/Notícia (obter em Blogs)
    + slug (string) - Caminho amigável do blog

+ Response 200 (application/json)

        {
            "id": "10",
            "codigoempresa": "310",
            "codigousuario": "44",
            "ativo": "1",
            "destaque": "0",
            "publicado": "1",
            "slug": "teste",
            "titulo": "Teste",
            "resumo": "teste",
            "conteudo": "<p>teste</p>",
            "tags": null,
            "autor": "teste",
            "criadoem": "2017-09-29 17:38:58",
            "publicarem": "2018-05-09",
            "exibicao": "0"
        }

+ Response 401 (text/plain)

        Chave de acesso inválida ou não informada

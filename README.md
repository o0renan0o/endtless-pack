# Endtless - Setup de Itens Customizados (sem plugin pago)

Este pacote permite usar modelos 3D premium no seu servidor **Minecraft 1.21.4 - 1.21.11+**
sem precisar de Oraxen / Nexo / ItemsAdder.

**Colecoes incluidas (5 packs, 39+ itens):**
- **What Collection** (Polygony) - 5 ferramentas (sword, axe, pickaxe, shovel, hoe)
- **Carnivoret Weapon Set V1** (EliteCreatures) - 18 itens:
  - 8 armas (sword, axe, hammer, scythe, spear, staff, bow com 3 estagios de tensao, shield com blocking)
  - 4 ferramentas (pickaxe, shovel, hoe, fishing rod com cast)
  - 4 armaduras (chestplate, leggings, boots, hat) - aparecem no CORPO do player
  - 2 cosmeticos (key, wing)
- **Asura Collection** - 7 itens estilo japones (sword, wings, 5 moedas: card, circle, emerald, square, triangle)
- **Demon Train** - 2 modelos infernais (locomotiva + vagao) com texturas animadas de fumaca
- **Zelda - Toffy Pack** - 7 itens lendarios:
  - Master Sword com swirl animado
  - Hylian Shield com modelo de blocking
  - Armadura completa do Link (hat, tunic, pants, boots) aparecendo no CORPO
  - Rupee cosmetico

**NAO incluido (motivo plugin-only):**
- Steam Train Coaster Pack - especifico do plugin EliteCreatures Roller Coaster

Funciona em **vanilla Paper 1.21.4+** usando:
- Resource Pack (modelos 3D + texturas + equipment assets)
- Datapack (comandos /function + 29 receitas + 5 loot tables + shop GUI)

## Features especiais implementadas

- ⚔ **Carnivoret Sword epica**: Sharpness 5 + Fire Aspect 2 + Looting 3 + Sweeping Edge 3 + Unbreaking 3 + Mending + dano extra via atributo
- 🏹 **Carnivoret Bow**: Power V + Punch II + Flame + Infinity (basicamente Hawkeye)
- 🔨 **Carnivoret Hammer**: Knockback II + dano extra +4 via atributo + knockback extra
- 🔱 **Carnivoret Spear**: Piercing III + reach estendido (+1.5 blocos!) via atributo
- 🪶 **Asura Wings** (elytra): da Speed I + Regen I AUTOMATICAMENTE quando equipada no peito
- 🪶 **Carnivoret Wing**: da Slow Falling enquanto na mao (cair como uma pena)
- 🚂 **Demon Train veiculo**: clica "Subir no Demon Train" e voce monta um minecart com o modelo do trem
- 📦 **Carnivoret Chest**: ender_chest com visual customizado (funcional ao colocar)
- 📦 **Spawn Decor**: comando que spawna decoracoes 3D no mundo (item_display entities)
- 💎 **5 loot tables**: drops aleatorios de cada colecao + lootbox "Legendary Treasure"

---

## O que tem nessa pasta

```
Endtless_Setup/
├── README.md                    <- este arquivo
├── 1_ResourcePack/              <- pasta expandida (edite aqui se quiser)
├── EndtlessPack.zip             <- pronto para HOSPEDAR online
├── 2_Datapack/                  <- pasta expandida (edite aqui se quiser)
└── EndtlessDatapack.zip         <- pronto para COLOCAR NO MUNDO
```

---

## INSTALAÇÃO - 4 PASSOS

### Passo 1 — Hospedar o Resource Pack

O Minecraft precisa baixar o pack de uma URL pública. Opções gratuitas:

**Opção A — GitHub (recomendado, mais profissional):**
1. Crie um repositório público em github.com (ex: `endtless-pack`)
2. Em "Releases" → "Create a new release"
3. Anexe o `EndtlessPack.zip`
4. Publique e copie o link direto do .zip
   (algo tipo: `https://github.com/seu-user/endtless-pack/releases/download/v1/EndtlessPack.zip`)

**Opção B — Dropbox / Google Drive:**
- Faça upload do .zip
- Gere link público
- **IMPORTANTE:** transforme em link direto:
  - Dropbox: troque `?dl=0` por `?dl=1` no final
  - Drive: use https://drive.usercontent.google.com/download?id=ID_DO_ARQUIVO

### Passo 2 — Configurar server.properties

No painel do BedHosting → Arquivos → `server.properties`:

```
resource-pack=https://SUA_URL_AQUI/EndtlessPack.zip
resource-pack-sha1=
require-resource-pack=true
resource-pack-prompt=Aceite o pack para ver os itens exclusivos do Endtless!
```

Para gerar o sha1 (recomendado, evita cache antigo):
- Mac/Linux: `shasum EndtlessPack.zip` no Terminal
- Online: https://emn178.github.io/online-tools/sha1_checksum.html
- Cole o hash em `resource-pack-sha1=`

Salva e reinicia o servidor.

### Passo 3 — Instalar o Datapack

No painel do BedHosting → Arquivos → entra na pasta do mundo
(geralmente `world/` ou o nome do seu mundo) → entra em `datapacks/`.

Faça upload de `EndtlessDatapack.zip` **sem extrair** (datapacks ficam zipados).

No console:
```
reload
```
ou reinicie o servidor.

Confirme com:
```
datapack list
```
Deve aparecer `[file/EndtlessDatapack.zip]` em "available datapacks".

Se não estiver enabled:
```
datapack enable "file/EndtlessDatapack.zip"
```

### Passo 4 — Testar no jogo

Entre no servidor (aceite o pack quando pedir) e teste:

**Loja com GUI bonita (recomendado):**
```
/trigger endtless_shop     <- qualquer player pode usar
/function endtless:shop    <- so admin/op
```

Vai abrir um menu clicavel no chat com todos os itens.

**Comandos diretos (admin):**

What Collection:
```
/function endtless:give_sword
/function endtless:give_axe
/function endtless:give_pickaxe
/function endtless:give_shovel
/function endtless:give_hoe
/function endtless:give_all          <- kit inteiro
/function endtless:guia              <- mostra receitas de craft
/function endtless:what/shop         <- sub-shop bonita
```

Asura Collection:
```
/function endtless:asura/shop              <- shop bonita
/function endtless:asura/give_sword
/function endtless:asura/give_wings        <- usa material elytra!
/function endtless:asura/give_card_coin
/function endtless:asura/give_circle_coin
/function endtless:asura/give_emerald_coin
/function endtless:asura/give_square_coin
/function endtless:asura/give_triangle_coin
/function endtless:asura/give_all
/function endtless:asura/give_coins        <- so as 5 moedas
```

Demon Train:
```
/function endtless:demon_train/shop
/function endtless:demon_train/give_train
/function endtless:demon_train/give_carriage
/function endtless:demon_train/give_all
```

Zelda - Toffy Pack:
```
/function endtless:toffy/shop
/function endtless:toffy/give_master_sword     <- Sharpness 5 + Smite 3
/function endtless:toffy/give_hylian_shield    <- com blocking animation
/function endtless:toffy/give_hat
/function endtless:toffy/give_tunic            <- aparece no corpo
/function endtless:toffy/give_pants
/function endtless:toffy/give_boots
/function endtless:toffy/give_rupee
/function endtless:toffy/give_armor            <- so armadura Link
/function endtless:toffy/give_all
```

Carnivoret Weapon Set:
```
/function endtless:carnivoret/shop                <- shop principal com categorias
/function endtless:carnivoret/give_sword          <- ESPADA EPICA (Sharp 5+Fire+Looting+SwpEdge+Mend+dmg extra)
/function endtless:carnivoret/give_bow            <- BOW LENDARIO (Power 5+Punch 2+Flame+Infinity)
/function endtless:carnivoret/give_hammer         <- martelo (KB 2+dmg+4+kb+1.5)
/function endtless:carnivoret/give_spear          <- lanca (Piercing 3 + reach +1.5)
/function endtless:carnivoret/give_pickaxe        <- picareta (Eff 5+Fortune 3+Mend)
/function endtless:carnivoret/give_chestplate     <- Prot 4 + Mend, aparece no corpo
/function endtless:carnivoret/give_chest          <- NOVO: ender_chest com visual Carnivoret
/function endtless:carnivoret/spawn_chest_decor   <- NOVO: spawna decor 3D no mundo
/function endtless:carnivoret/remove_decor        <- NOVO: remove decoracoes proximas
... (mais 12 functions - veja /function endtless:carnivoret/shop)
```

NOVAS FEATURES de Asura:
```
Asura Wings agora da Speed I + Regen I AUTOMATICAMENTE quando equipada no peito!
(Detectado via /execute if items entity @s armor.chest *[item_model="endtless:asura_wings"])
```

NOVAS FEATURES de Demon Train:
```
/function endtless:demon_train/ride               <- NOVO: monta minecart com modelo do trem
/function endtless:demon_train/ride_carriage      <- NOVO: monta minecart com modelo do vagao
/function endtless:demon_train/dismount           <- NOVO: desce e limpa entidades
```

LOOT TABLES (drops aleatorios):
```
/function endtless:loot/shop                          <- GUI da lootbox
/function endtless:loot/give_carnivoret_random        <- 1 item aleatorio do Carnivoret
/function endtless:loot/give_zelda_random             <- 1-2 itens aleatorios Zelda
/function endtless:loot/give_asura_random             <- 1-2 itens aleatorios Asura
/function endtless:loot/give_demon_train_random       <- item aleatorio Demon Train
/function endtless:loot/give_legendary_treasure       <- 1-3 itens de QUALQUER pack (lendario)
/function endtless:loot/place_treasure_chest          <- coloca bau no chao com loot table

Ou usar diretamente:
/loot give @p loot endtless:carnivoret_random
/loot give @p loot endtless:legendary_treasure
/setblock ~ ~ ~ minecraft:chest{LootTable:"endtless:legendary_treasure"}
```

**Craftar na mesa de craft:**
- Receitas vanilla disponiveis (veja /function endtless:guia)
- Use o livro de receitas do Minecraft pra ver visualmente

Pronto. Os itens aparecem com modelo 3D vermelho/branco, nome em vermelho, lore temática e Unbreaking 3.

---

## Como dar para outros jogadores

Funções por padrão dão pra quem executa. Para dar pra outro:

```
/execute as JogadorAlvo run function endtless:give_sword
```

Ou crie uma função custom em `data/endtless/function/give_to_player.mcfunction`:
```
give @p netherite_sword[item_model="endtless:what_sword",...]
```
E use `/function endtless:give_to_player` apontando para o player mais proximo.

---

## Restringir comandos a admin/VIP

Por padrão, qualquer player com permissão de comando consegue rodar /function.
Para restringir:
- Use **LuckPerms** + permissão `minecraft.command.function`
- Ou crie um plugin de loja/crates que execute as funções via console

Exemplo com LuckPerms:
```
lp group default permission set minecraft.command.function false
lp group admin permission set minecraft.command.function true
lp group vip permission set minecraft.command.function true
```

---

## Integração com eventos (sugestões)

Use as funções como recompensa de:

| Evento | Recompensa |
|---|---|
| PvP Royale (sex 20h) | `/execute as @p[scores={pvp_wins=1..}] run function endtless:give_sword` |
| Caça ao Tesouro (sab 18h) | `/function endtless:give_pickaxe` |
| Boss Battle (dom 16h) | `/function endtless:give_all` (drop raro) |
| Crate VIP | Plugin de crate executa a função |

---

## Customizar nomes, lore, atributos

Edite os arquivos em `2_Datapack/data/endtless/function/*.mcfunction`.

Sintaxe completa de componentes 1.21.4:
- `item_model="endtless:what_sword"` — qual modelo usar
- `item_name='{"text":"Nome","color":"#ff4655"}'` — nome do item
- `lore=['{"text":"linha1"}','{"text":"linha2"}']` — descrição
- `enchantments={levels:{"minecraft:sharpness":5}}` — encantamentos
- `attribute_modifiers=[{type:"minecraft:generic.attack_damage",amount:8,operation:"add_value",slot:"mainhand"}]` — atributos
- `unbreakable={}` — irrompivel
- `glint={value:true}` — brilho fake (sem encantamento)

Depois de editar, rezipe a pasta `2_Datapack/` mantendo `pack.mcmeta` e `data/` na raiz, e reupload.

---

## Recursos avancados que ja foram implementados

- **Bow Carnivoret** com 3 estagios de tensao (vanilla 1.21.4+ via item definition condition)
- **Shield Carnivoret** com modelo separado quando o player ta bloqueando
- **Fishing Rod Carnivoret** muda de modelo quando o player joga a linha (cast)
- **Armadura Carnivoret + Zelda Link** aparece NO CORPO do player (sistema equippable + equipment assets)
- **Sistema de trigger** (/trigger endtless_shop) - qualquer player abre a shop sem permissao admin
- **Shop com sub-menus clicaveis** por categoria + Loot Shop dedicada
- **29 receitas vanilla** (5 What + 17 Carnivoret + 7 Zelda)
- **5 loot tables** com drops ponderados (raros = peso menor)
- **Detecao de itens em uso** via `/execute if items` (1.21.4+) - permite efeitos automaticos
- **Demon Train veiculo** usa system de mount nativo (minecart + item_display + ride command)

## Por que essa abordagem em vez de plugin?

- **Gratis pra sempre** — sem assinatura de plugin
- **Vanilla puro** — sobrevive a updates do Minecraft melhor
- **Performance** — zero overhead de plugin
- **Resource pack centralizado** — entrega automatica pelo proprio servidor

Limitacoes restantes:
- Demon Train ride: monta minecart, mas precisa de trilhos para se mover (vanilla minecart)
- Master Sword swirl: textura overlay funciona, mas rotacao automatica so com Optifine
- Itens Demon Train sao paper "decorativos" segurados na mao - nao tem fisica de trem
- Override de loot table vanilla (end_city, bastion): pulado para evitar conflitos com updates do Minecraft. Os admins usam /function endtless:loot/give_* manualmente em eventos ou colocam baus com /function endtless:loot/place_treasure_chest

## Integrando loot tables em eventos do servidor

Voce pode injetar drops nos eventos do Endtless usando estes comandos no console:

```
# PvP Royale - vencedor recebe lootbox lendaria
execute as <vencedor> run function endtless:loot/give_legendary_treasure

# Boss Battle - boss dropa Carnivoret aleatorio
data merge entity <boss_uuid> {DeathLootTable:"endtless:carnivoret_random"}

# Caca ao Tesouro - colocar bau com loot
execute at <coordenada> run setblock ~ ~ ~ chest{LootTable:"endtless:legendary_treasure"}

# Crate semanal - VIP recebe drop aleatorio
execute as @a[tag=vip] run loot give @s loot endtless:zelda_random
```

---

## Credito

Modelos 3D: Polygony Creation Co., Ltd. (Pack pago no MCModels)
Setup vanilla por: Endtless
```

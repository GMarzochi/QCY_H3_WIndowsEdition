# QCY H3 Controller

App desktop para Windows que controla o fone de ouvido **QCY H3** via Bluetooth Low Energy (BLE).

## Funcionalidades

- **Conexão BLE** — escaneia e conecta ao fone
- **Modos de ruído** — ANC Desligado, Transparência, ANC Baixo, ANC Médio, ANC Alto
- **Equalizador de 10 bandas** — 55 Hz até 22 kHz, ajuste em tempo real
- **Presets de EQ** — Custom, Default, Pop, Heavy Bass, Rock, Soft, Classic
- **Game Mode** — ativa o modo de baixa latência
- **Bateria** — exibe o nível e atualiza a cada 60 segundos

## Requisitos

- Windows 10/11 com Bluetooth BLE
- Python 3.11+

```
pip install PySide6 bleak
```

## Executar

```
python app.py
```

## Protocolo

Usa o protocolo **JieLi RCSP** sobre BLE GATT:
- Serviço: `0000a002-0000-1000-8000-00805f9b34fb`
- Write: `00000001-0000-1000-8000-00805f9b34fb`
- Notify: `00000002-0000-1000-8000-00805f9b34fb`

## Estrutura

| Arquivo | Descrição |
|---------|-----------|
| `app.py` | Entrada da aplicação |
| `main_window.py` | Interface gráfica (PySide6) |
| `ble_worker.py` | Worker BLE em thread separada |
| `h3_device.py` | Protocolo do dispositivo QCY H3 |
| `rcsp.py` | Implementação do protocolo RCSP/JieLi |

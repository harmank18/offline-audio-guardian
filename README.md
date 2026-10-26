# Offline Audio Guardian for Assistive Care

VLSID 2027 Design Contest entry, Platform 2: Renesas RA6E2 QuickConnect Beginner Kit.

**Team:** Aishan Nikam, Ayush Shukla, Harman Kishnadwala, Prashanth Kannan
**Faculty mentor:** Professor Akshay Madan

> Status: planning stage. The kit arrives 9 Nov and the final submission is 4 Dec.
> No results yet; measured results will be added here as we get them.

## Idea
An always-on, fully offline audio guardian for people who cannot easily reach a
switch, phone or caregiver (elderly, bedridden, mobility-impaired). One digital
microphone feeds two small neural networks running on the microcontroller:

- **Keyword spotting:** an emergency word plus a few room-control commands
- **Sound-event detection:** selected non-speech sounds such as an alarm or glass breaking

Commands switch devices in a low-voltage tabletop room model. Emergencies trigger
a local buzzer and a Wi-Fi/BLE alert. On-board sensors drive an automatic comfort mode.

## Why this approach
- **Offline and private:** no cloud, and no raw audio leaves the device
- **Small hardware:** speech and sound events within the board's 40 KB SRAM budget
- **Built for Indian users:** we plan to record our own English/Hindi data through the kit's mic
- **Safety first:** confidence thresholds, confirmation for critical actions,
  a panic button and fallback control paths
- **Measured, not claimed:** accuracy, false-reject rate of the emergency word,
  latency, memory and power will be reported from real tests

## Datasets (planned)
| Dataset | Use | Licence |
|---|---|---|
| Google Speech Commands v2 | Keyword pre-training | see dataset page |
| Own recordings | Emergency word, Hindi, kit-mic data | our own |
| ESC-50 | Sound-event model | CC BY-NC |
| MUSAN (noise part) | Noise augmentation | CC BY 4.0 |

Audio data is not stored in this repo.

## Plan
1. Before the kit arrives: data pipeline and a baseline keyword model in Python
2. Week 1 on the kit: microphone capture, model on device, memory and latency check
3. Week 2: own-data fine-tuning, sound-event model, actuation, dashboard
4. Week 3: sensor auto-mode, safety logic, full evaluation
5. Final days: power measurements, demo video, submission

## References
- P. Warden, Speech Commands, arXiv:1804.03209
- Y. Zhang et al., Hello Edge: Keyword Spotting on Microcontrollers, arXiv:1711.07128

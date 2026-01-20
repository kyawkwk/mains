# Architecture Overview

Below is an architecture overview of the Rock-Paper-Scissors game logic shown in `main.py`, visualized using a Mermaid flowchart. This diagram illustrates the flow from player input to game result determination.

```mermaid
flowchart TD
    Start([Start])
    Input["Player Input: Gunting/Batu/Kertas"]
    Komputer["Komputer chooses randomly <br/> from Gunting, Batu, or Kertas"]
    Compare{"Compare Player and Komputer Choices"}
    Seri["Print: Seri!"]
    Menang["Print: Kamu Menang! <br/> (Player beats Komputer)"]
    Kalah["Print: Kamu Kalah! <br/> (Komputer beats Player)"]
    Salah["Print: Pilihan yang kamu masukan salah..."]
    Loop["Loop for next round"]

    Start --> Komputer
    Komputer --> Input
    Input --> Compare

    Compare -- Same Choice --> Seri
    Compare -- Player wins --> Menang
    Compare -- Komputer wins --> Kalah
    Compare -- Invalid input --> Salah

    Seri --> Loop
    Menang --> Loop
    Kalah --> Loop
    Salah --> Loop

    Loop --> Input
```

**Legend:**
- _Player Input_: Player selects "Gunting" (Scissors), "Batu" (Rock), or "Kertas" (Paper)
- _Komputer_: Computer selects randomly from the same options
- _Comparison_: Determines if the game is a draw, win, or loss
- _Loop_: Continues the game for multiple rounds

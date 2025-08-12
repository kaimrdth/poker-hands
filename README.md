# Poker Hands Visualizer

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=flat&logo=javascript&logoColor=%23F7DF1E)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=flat&logo=css3&logoColor=white)

try it [here](https://bit.ly/handsofpoker)

![Demo](demo.gif)

Generates and displays poker hands in real-time based on user input.

## Features

- Type poker hand names to generate 5 example hands
- Interactive text input with validation and color coding
- Auto-refreshing hands every 12 seconds
- Keyboard navigation with arrow keys
- Visual card representations using Unicode emojis
- Support for all standard poker hands plus random generation
- Hands displayed in order from strongest to weakest (top to bottom)
- Random mode highlights the winning hand among the 5 generated

## Usage

Type any of these hand types:
- `pair`, `two pair`, `three of a kind`
- `straight`, `flush`, `full house`
- `four of a kind`, `straight flush`, `royal flush`
- `random`

### Controls
- **Enter**: Deal new hands of current type
- **↑/↓**: Navigate through hand types
- **Mouse hover**: Preview hand types from sidebar

## Application Flow

```mermaid
graph TD
    A[User Types Input] --> B{Valid Hand Type?}
    B -->|Yes| C[Generate 5 Hands]
    B -->|No| D[Show Error Message]
    C --> E[Animate Card Reveal]
    E --> F[Display Cards with Suit Colors]
    F --> G[Start Auto-refresh Timer]
    G --> H[Wait 12 seconds]
    H --> I{Still Same Hand?}
    I -->|Yes| C
    I -->|No| J[Stop Timer]
    
    K[Arrow Key Press] --> L[Navigate Hand Types]
    L --> M[Update Input Field]
    M --> C
    
    N[Enter Key] --> O[Re-deal Current Hand]
    O --> C
    
    P[Hover Sidebar] --> Q[Preview Hand Type]
    Q --> C
```

## Technical Details

- Single HTML file with embedded CSS and JavaScript
- Uses Unicode playing card emojis (🂡-🂾)
- Implements algorithms for each poker hand type
- No external dependencies or build process required
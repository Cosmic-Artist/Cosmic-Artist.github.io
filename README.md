
# Julian Smith Programming Portfolio
An example portfolio for Programming I at Columbia College Chicago.

## 🐻 C#

> 🏅 PROG 101 - Programming I

---

### 🎮 Ordle - Word Guessing Game

A WPF word-guessing game where users guess a secret 5-letter word, inspired by Wordle.

* Built with WPF and C#
* Random solution word loaded from external text file
* Color-coded hints (Green = Correct, Yellow = Wrong Place, Grey = Incorrect)

<img width="948" alt="Ordle game" src="https://github.com/user-attachments/assets/d0a75591-b20e-4c69-b5af-e8dce156c531" />


---

### ☕ Coffee Ordering App

A console-based simulation where users order customized coffee drinks.

* Interface-based design
* Demonstrates Object-Oriented Programming (OOP) principles
* Hot and Cold drink selections with temperature simulation
<img width="576" alt="Cofee game" src="https://github.com/user-attachments/assets/d62f13c0-99d8-4353-a819-5b12002e4999" />


---

### 📈 Stocks Event Handler App

A console stock market simulation where prices update live based on C# events and delegates.

* Uses event-driven programming
* Displays real-time stock price changes
* Console application built in C#

<img width="798" alt="Stock app" src="https://github.com/user-attachments/assets/d23ae856-1ac7-41fa-b3d8-72160afde8bb" />


---

### 🃏 Project 2 - Card Games Collection

A C# console application featuring a collection of simple card games.

* Play Higher/Lower, Same or Different, and Highest Match
* Menu-based game selection
* Reusable `Deck` and `Card` system


<img width="763" alt="Project 2" src="https://github.com/user-attachments/assets/3339a253-bd8c-42d8-9f9d-eacb311942de" />

---

### 🖼️ Project 3 - Word Guessing Game WPF

A refined version of Ordle made with advanced WPF UI techniques.

* GUI created with WPF (XAML)
* Real-time validation
* Fully dynamic word loading

<img width="875" alt="project 3 game" src="https://github.com/user-attachments/assets/551cc0a0-9e1f-4330-9d8d-0b601c27a284" />


---

## 🛠️ Tools Used
- Visual Studio 2022
- C# (.NET 8.0)
- GitHub
- GitHub Pages
- WPF for GUI Development
- Console Applications for Event-Driven Programming

---

## 🔗 Links

- [GitHub Profile - Cosmic-Artist](https://github.com/Cosmic-Artist)
- [Live Portfolio Site - Coming Soon!](https://cosmic-artist.github.io)

---

## 📜 Code Sample (from Ordle Project)

```csharp
private void Button_Click(object sender, RoutedEventArgs e)
{
    if (currentRow >= rows)
    {
        GameMessage.Text = "Game Over!";
        return;
    }

    string guess = PlayerInput.Text.Trim().ToLower();
    if (guess.Length != cols)
    {
        GameMessage.Text = "Enter a 5-letter word!";
        return;
    }

    if (!engine.IsWordInList(guess))
    {
        GameMessage.Text = "Invalid word!";
        return;
    }

    for (int j = 0; j < cols; j++)
    {
        TextBlocks[currentRow, j].Text = guess[j].ToString().ToUpper();
        if (guess[j] == engine.Solution[j])
        {
            TextBlocks[currentRow, j].Background = Brushes.Green;
        }
        else if (engine.Solution.Contains(guess[j]))
        {
            TextBlocks[currentRow, j].Background = Brushes.Yellow;
        }
        else
        {
            TextBlocks[currentRow, j].Background = Brushes.LightGray;
        }
    }

    if (guess == engine.Solution)
    {
        GameMessage.Text = "You Win!";
        SubmitButton.IsEnabled = false;
    }
    else
    {
        currentRow++;
        if (currentRow == rows)
        {
            GameMessage.Text = $"Out of tries! Solution: {engine.Solution.ToUpper()}";
            SubmitButton.IsEnabled = false;
        }
    }

    PlayerInput.Clear();
}
```

> Code sample from the Ordle word guessing game project built in C# WPF.

---

For more details on Markdown formatting, see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

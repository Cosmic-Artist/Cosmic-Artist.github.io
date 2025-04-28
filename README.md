
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

<img width="600" alt="Ordle Game Screenshot" src="images/Ordle%20game.png" />

---

### ☕ Coffee Ordering App

A console-based simulation where users order customized coffee drinks.

* Interface-based design
* Demonstrates Object-Oriented Programming (OOP) principles
* Hot and Cold drink selections with temperature simulation

<img width="600" alt="Coffee Game Screenshot" src="images/Cofee%20game.png" />

---

### 📈 Stocks Event Handler App

A console stock market simulation where prices update live based on C# events and delegates.

* Uses event-driven programming
* Displays real-time stock price changes
* Console application built in C#

<img width="600" alt="Stocks App Screenshot" src="images/Stock%20app.png" />

---

### 🃏 Project 2 - Card Games Collection

A C# console application featuring a collection of simple card games.

* Play Higher/Lower, Same or Different, and Highest Match
* Menu-based game selection
* Reusable `Deck` and `Card` system

<img width="600" alt="Card Games Project Screenshot" src="images/Project%202.png" />

---

### 🖼️ Project 3 - Word Guessing Game WPF

A refined version of Ordle made with advanced WPF UI techniques.

* GUI created with WPF (XAML)
* Real-time validation
* Fully dynamic word loading

<img width="600" alt="Project 3 Game Screenshot" src="images/project%203%20game.png" />

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

import random

def roll_dice():
    return random.randint(1, 6)

def main():
    print("Welcome to the Dice Rolling Competition!")

    # Taking player names as input
    players = []
    for i in range(4):
        name = input(f"Enter the name of player {i + 1}: ")
        players.append(name)

    print("\nLet the game begin!\n")

    # Dictionary to store players' scores
    scores = {}

    # Each player rolls the dice
    for player in players:
        input(f"{player}, press Enter to roll the dice...")
        roll = roll_dice()
        scores[player] = roll
        print(f"{player} rolled a {roll}\n")

    # Determine the winner(s)
    max_score = max(scores.values())
    winners = [player for player, score in scores.items() if score == max_score]

    print("Game Over!\n")
    print("Final Scores:")
    for player, score in scores.items():
        print(f"{player}: {score}")

    if len(winners) > 1:
        print("\nIt's a tie between:")
        for winner in winners:
            print(winner)
    else:
        print(f"\nThe winner is {winners[0]}! Congratulations!")

if __name__ == "__main__":
    main()

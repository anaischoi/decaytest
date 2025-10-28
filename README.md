def get_risk_score():
    print("Tooth Decay Risk Calculator\n")

    # Sugar intake
    sugar = input("How often do you eat sugary foods? (Type low, medium, or high: low 0-25g / medium 25-50g / high 50+): ").lower()
    if sugar == "low(0-25g)":
        sugar_score = 1
    elif sugar == "medium(25-50g)":
        sugar_score = 2
    else:
        sugar_score = 3

    # Brushing frequency
    brushing = int(input("How many times do you brush per day? (0-3+): "))
    if brushing >= 2:
        brushing_score = 1
    elif brushing == 1:
        brushing_score = 2
    else:
        brushing_score = 3

    # Flossing frequency
    flossing = int(input("How many times do you floss per week? (0-7+): "))
    if flossing >= 3:
        flossing_score = 1
    elif flossing >= 1:
        flossing_score = 2
    else:
        flossing_score = 3

    # Water intake
    water = int(input("How many glasses of water do you drink per day? "))
    if water >= 6:
        water_score = 1
    elif water >= 3:
        water_score = 2
    else:
        water_score = 3

    # Dental visits
    dental_visit = input("Do you visit the dentist regularly? (yes/no): ").lower()
    if dental_visit == "yes":
        dental_score = 1
    else:
        dental_score = 3

    # Total risk score
    total_score = sugar_score + brushing_score + flossing_score + water_score + dental_score

    # Risk level
    if total_score <= 6:
        risk = "Low"
    elif total_score <= 10:
        risk = "Moderate"
    else:
        risk = "High"

    print(f"\nYour total risk score is: {total_score}")
    print(f"Your tooth decay risk is: {risk}")

# Run the calculator
get_risk_score()

# IntegrationProjectFinal

"""This program explores the use of
    simple operators in a variety of
    different contexts. The listed
    requirements for the integration
    project should be followed
    approximately sequential with
    this program"""


def main():
    """This program explores the use of
    simple operators in a variety of
    different contexts. The listed
    requirements for the integration
    project should be followed
    approximately sequential with
    this program"""
    __author__ = "Gunnar Stewart"

    import math

    def integervalue():
        """This function acts as a guardian for user input guaranteeing an
        integer value is entered in order to prevent the program from
        crashing. The parameters accepted are the user input, if said input
        is an integer, the program will continue without problems, if the
        input is not an integer, the program will inform the user and ask
        for another input. """
        userinput = True
        while userinput:
            try:
                useriinput = int(input())
                userinput = False
                return useriinput
            except ValueError:
                print("Not an Integer, try again")

    def floatvalue():
        """This function acts as a guardian for user input guaranteeing an real
        value is entered in order to prevent the program from crashing. The
        parameters accepted are the user input, if said input is a real number,
        the program will continue without problems, if the input is not a real
        number, the program will inform the user and ask for another input."""
        userinput = True
        while userinput:
            try:
                useriinput = float(input())
                userinput = False
                return useriinput
            except ValueError:
                print("Not a real number, try again")

    def nonzerofloatvalue():
        """
        Garentees that whatever the user inputs, is that it is a real nonzero
        number. If user input fails to pass this guardian, they will be
        prompted to do it again. :return:
        """
        userinput = True
        while userinput:
            try:
                useriinput = float(input())
                if useriinput != 0:
                    userinput = False
                    return useriinput
                else:
                    print("Must be a non-zero number, try again")
                    userinput = True
            except ValueError:
                print("Not a real number, try again")

    def oneortwo():
        """
        This function restricts user input strictly to either a 1 or 2. If
        the user input is not a one or two, the user will be prompted to do
        it again. :return:
        """
        userinput = True
        while userinput:
            try:
                useriinput = int(input())
                if useriinput == 1:
                    userinput = False
                    return useriinput
                elif useriinput == 2:
                    userinput = False
                    return useriinput
                else:
                    print("Please enter a 1 or 2, try again")
                    userinput = True
            except ValueError:
                print("Please enter a 1 or 2, try again")

    def greaterthanone():
        """
        This function restricts user input to an integer value greater than 1,
        else, the user will be prompted to try again. :return:
        """
        userinput = True
        while userinput:
            try:
                useriinput = int(input())
                if useriinput > 1:
                    userinput = False
                    return useriinput
                else:
                    print("Please enter a integer greater than 1, try again")
                    userinput = True
            except ValueError:
                print("Please enter a integer greater than 1, try again")

    # Input function
    username = input("What is your name? ")
    # Greets user with sep= and end= arguments
    print("Welcome", username, end="!")

    print("\n\nGive me your favorite integer value: ")
    base_number = integervalue()
    integerbasenumber = int(base_number)
    # Exponent operation
    print("Here is your favorite integer cubed:", integerbasenumber ** 3)
    cubed = float(integerbasenumber ** 3)
    # Multiplication operation
    print("Here is your number cubed and then multiplied by 1/2:", cubed * 0.5)

    print("\nGive me any real number: ")
    real_number = floatvalue()
    floatrealnumber = float(real_number)
    # Division operation
    print("If we divide your real number by 2, we get", floatrealnumber / 2.0)

    print("\nGive me a real non-zero number: ")
    divisor = nonzerofloatvalue()
    floatdivisor = float(divisor)
    # Dividend and floor division
    print("Your  number goes into 4 at least", 4 // floatdivisor, 'times')
    # The divisor is required to be
    # a positive real number in
    # order for remainder to work
    # correctly because negative
    # floats seem to cause strange
    # outputs.
    print("The remainder being approximately", 4 % floatdivisor)

    print("\nEnter first real number: ")
    num1 = floatvalue()
    print("Enter second real number: ")
    num2 = floatvalue()
    floatnum1 = float(num1)
    floatnum2 = float(num2)
    # Addition operation
    print("The sum of your first and second real numbers are",
          floatnum1 + floatnum2)
    # Subtraction operation
    print(
        "The difference of your first and second real numbers respectively "
        "are",
        floatnum1 - floatnum2)

    print(
        "\nEnter a whole number for how many times you want to scream 'AMONG "
        "US!': ")
    repetition = integervalue()
    integerrepetition = int(float(repetition))
    # Repetition of a string
    print("AMONG US! " * integerrepetition)

    print(
        "\nWhat is the appropriate punctuation to end the following sentence:")
    print("'Sarah, did you take out the trash like I asked'")
    p1 = input("Your answer: ")
    # concatenation using '+' for strings
    print("Sarah, did you take out the trash like I asked" + p1)

    # We assume we are dealing with a rectangle in the xy-plane such that
    # negative geometries are regarded equivalent to positive geometries.
    print("Enter a numeric side length of a rectangle: ")
    side1 = floatvalue()
    print("Enter a another numeric side length of a rectangle: ")
    side2 = floatvalue()
    recarea = abs(side1 * side2)
    if side1 == side2:
        print("You have a special case of rectangle, a square with area",
              recarea)
    else:
        print("The area of your rectangle is", recarea)

    # Guessing game using a loop properties of calling a
    # defined function
    def guessgame():
        """This functionacts as the structure for a number guessing game,
        completely builot upon if and elif statements. What goes in is user
        inpout of an integer, and what comes out are string statements guiding
        the user on their progress """
        print("\nGuess the integer I am thinking of between 1 and 10: ")
        guessnum = integervalue()
        if guessnum == 9:
            print("That's correct!")
        elif guessnum % 2 == 0:
            print("Hint: It is an odd number.")
            guessgame()
        elif guessnum <= 5:
            print("Hint: The number is greater than 5.")
            guessgame()
        elif guessnum != 9:
            print("Close, try again.")
            guessgame()

    guessgame()

    # The following code uses the theorem of Papus to
    # find the volume of a torus.
    def voltorus(crossArea, distance):
        """This function uses the theorem of pappus to find the volume of a
        torus. User input is not accounted in this function itself, but is
        passed through its parameters when needed. """
        volume = crossArea * distance
        print("The volume of your torus is: ", format(volume, '.2f'))

    print("Lets find the volume of a torus of your choosing.")
    print(
        "Pick a cross-sectional shape for your torus (1=Ellipse, "
        "2=Rectangle): ")
    shape = oneortwo()
    if shape == 1:
        print("Enter value for x semi-axis of ellipse: ")
        xrad = floatvalue()
        print("Enter value for y semi-axis of ellipse: ")
        yrad = floatvalue()
        print("Enter the inner radius of your torus: ")
        innerrad = floatvalue()
        dis = abs(2 * math.pi * (innerrad + xrad))
        area = abs(math.pi * xrad * yrad)
        voltorus(area, dis)
    elif shape == 2:
        print("Enter height of rectangle: ")
        side1 = floatvalue()
        print("Enter width of rectangle: ")
        side2 = floatvalue()
        print("Enter the inner radius of your torus: ")
        innerrad = floatvalue()
        dis = abs(2 * math.pi * (innerrad + side2 / 2))
        area = abs(side1 * side2)
        voltorus(area, dis)

    print("Give a real number:")
    elnum1 = floatvalue()
    if elnum1 > 0 and elnum1 % 1 == 0:
        print("Your number is a natural number.")
    if not (-9 <= elnum1 <= 9) or elnum1 % 1 != 0:
        print("Your number is not a single digit integer.")
    if elnum1 % 1 == 0 and elnum1 < 0:
        print("Your number is a negative integer.")

    n = len(input("Type something: "))
    for i in range(1, n + 1):
        print("Wow, that was pointless.")

    print("Give me a positive integer greater than 1: ")
    n2 = greaterthanone()
    while n2 > 0:
        n2 -= 1
        print(n2 + 1)


if __name__ == "__main__":
   main()

# quadratic_equation
#enter a, b, and c values to find roots

import math

def quadratic_equation(a, b, c):
  """
  Solves a quadratic equation of the form ax^2 + bx + c = 0.

  Args:
    a: The coefficient of the x^2 term.
    b: The coefficient of the x term.
    c: The constant term.

  Returns:
    A tuple of two floats, representing the roots of the quadratic equation.
  """

  # Calculate the discriminant.
  discriminant = b**2 - 4*a*c

  # If the discriminant is negative, then there are no real roots.
  if discriminant < 0:
    return None

  # If the discriminant is zero, then there is one repeated root.
  elif discriminant == 0:
    return (-b / (2*a),)

  # If the discriminant is positive, then there are two distinct roots.
  else:
    return ((-b + math.sqrt(discriminant)) / (2*a), (-b - math.sqrt(discriminant)) / (2*a))

if __name__ == "__main__":
  # Get the coefficients of the quadratic equation from the user.
  a = float(input("Enter the coefficient of the x^2 term: "))
  b = float(input("Enter the coefficient of the x term: "))
  c = float(input("Enter the constant term: "))

  # Solve the quadratic equation.
  roots = quadratic_equation(a, b, c)

  # Print the roots of the quadratic equation.
  if roots is None:
    print("There are no real roots.")
  elif len(roots) == 1:
    print("There is one repeated root:", roots[0])
  else:
    print("There are two distinct roots:", roots[0], roots[1])

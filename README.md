# chem_bond
import numpy as np

def calculate_distance(atom1, atom2):
    """
    Calculate the Euclidean distance between two atoms.

    Parameters:
        atom1 (numpy.ndarray): Coordinates of atom 1.
        atom2 (numpy.ndarray): Coordinates of atom 2.

    Returns:
        float: Euclidean distance between the atoms.
    """
    return np.linalg.norm(atom1 - atom2)

def calculate_bond_order(distance, bond_length, bond_order_max):
    """
    Calculate the bond order based on the distance between two atoms,
    bond length, and maximum bond order.

    Parameters:
        distance (float): Distance between the atoms.
        bond_length (float): Equilibrium bond length.
        bond_order_max (float): Maximum bond order.

    Returns:
        float: Bond order.
    """
    return bond_order_max * (1 - (distance / bond_length))
# Get user input for atom coordinates
x1, y1, z1 = map(float, input("Enter coordinates of atom 1 (x y z): ").split())
x2, y2, z2 = map(float, input("Enter coordinates of atom 2 (x y z): ").split())
atom1 = np.array([x1, y1, z1])
atom2 = np.array([x2, y2, z2])

# Get user input for equilibrium bond length and maximum bond order
bond_length = float(input("Enter equilibrium bond length: "))
bond_order_max = float(input("Enter maximum bond order: "))

# Calculate distance between atoms
distance = calculate_distance(atom1, atom2)

# Calculate bond order
bond_order = calculate_bond_order(distance, bond_length, bond_order_max)

# Print results
print("Bond length:", distance)
print("Bond order:", bond_order)

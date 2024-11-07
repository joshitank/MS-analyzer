python

# ms-analyzer.py

import pandas as pd

# Constants
PROTON_MASS = 1.007276  # Mass of a proton in Da

# Calculate m/z value of charge states z=1-max_charge, with given max_charge
def calculate_mz(peptide_mass, max_charge):
 """
    Calculate the m/z values for a peptide given its mass and a range of charge states.
    
    Args:
    - peptide_mass (float): The mass of the peptide.
    - max_charge (int): The maximum charge state to calculate m/z values for.
    
    Returns:
    - mz_values (dict): Dictionary of m/z values for each charge state from 1 to max_charge.
    """
mz_values = {}
    for charge in range(1, max_charge + 1):
        mz_values[charge] = (peptide_mass + (charge * PROTON_MASS)) / charge
    return mz_values

# find matches with given charge states in the MS data
def find_matches(data, peptide_masses, max_charge, tolerance=0.01):
"""
    Searches for m/z values in the data that match target m/z values
    within a specified tolerance for given peptide masses and a range of charge states.
    
    Args:
    - data (pd.DataFrame): Mass spectrometry data with columns 'm/z' and 'intensity'.
    - peptide_masses (list of float): List of target peptide masses.
    - max_charge (int): Maximum charge state to consider.
    - tolerance (float): Allowed tolerance for m/z matching.
    
    Returns:
    - matches (list of dict): List of matches with peptide mass, charge, target m/z, and found m/z.
    """

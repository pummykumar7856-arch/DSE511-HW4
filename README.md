# DSE511 Homework 4: Refactoring and Documenting Code

## 1. Original Code
The original code was developed for Homework 3 and contained sorting and membership-testing experiments. The code worked, but experiment logic, configuration, result collection, and plotting were mixed together in notebook cells. Some values also depended on global variables.

## 2. Refactoring Changes
I refactored the code by separating the main tasks into reusable functions.
The main changes were:

- Created `run_sorting_experiment()` for the sorting benchmark.
- Created `plot_sorting_results()` for sorting plots.
- Improved function documentation using docstrings.
- Updated `gen_ids()` to receive the random number generator as a parameter.
- Updated `membership_timing()` to use parameters for configuration.
- Created `run_membership_experiment()` for the membership benchmark.
- Created `plot_membership_results()` for the membership plot.
- Added error handling for invalid membership structure types.
- Kept the main experiment inputs and output structure consistent with the original code.

These changes make the code easier to read, reuse, test, and modify.

## 3. Testing and Verification
I added tests for a normal insertion-sort case and an edge case using an empty list. Both tests passed successfully.
I also verified the refactored sorting experiment by checking that the expected output columns and input sizes were preserved.

## 4. Why the Refactoring Helps

The refactored code separates configuration, experiment execution, and visualization. Individual functions can now be tested and reused without rewriting the entire experiment.
For example, the sorting experiment can be run with different input sizes by calling `run_sorting_experiment()`. The membership experiment can similarly be reused with different collection sizes and numbers of queries.

## 5. Future Use

The refactored structure will make it easier for me or another collaborator to modify the experiments, add new sorting methods or data structures, and test individual components.

## 6. Limitations

The experiments are affected by computer performance and runtime conditions. Insertion sort also becomes very slow as the input size increases, so a maximum manageable input size is used for the insertion-sort benchmark.

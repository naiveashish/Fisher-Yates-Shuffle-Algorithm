# Fisher-Yates Shuffle Algorithm

The Fisher-Yates shuffle algorithm, also known as the Knuth shuffle, is a popular method for randomly shuffling the elements of an array in JavaScript. It ensures a truly random permutation of elements, making it useful in various applications such as games, simulations, and data randomization.

## How it Works

The Fisher-Yates shuffle algorithm works by iteratively swapping each element in the array with a randomly selected element that precedes it. This process continues until all elements have been shuffled.

Here's a simplified overview of the algorithm:

1. Start at the last element of the array.
2. Randomly select an element from the unshuffled part of the array, including the current element.
3. Swap the selected element with the current element.
4. Move one step back in the array and repeat steps 2-3 until reaching the first element.

By following these steps, the algorithm ensures that each element has an equal chance of ending up at any position in the shuffled array, resulting in a truly random permutation.

## Usage in JavaScript

The Fisher-Yates shuffle algorithm can be implemented in JavaScript using a simple function. Here's an example implementation:

```javascript
function fisherYatesShuffle(array) {
    for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]]; // Swap elements
    }
    return array;
}

// Example usage:
const originalArray = [1, 2, 3, 4, 5];
const shuffledArray = fisherYatesShuffle(originalArray);
console.log(shuffledArray);

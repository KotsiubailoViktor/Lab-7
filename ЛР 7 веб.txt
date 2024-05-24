// Функція для перевірки, чи є аргумент числом, та визначення парності
function checkNumber(input) {
    if (typeof input === 'number') {
        return input % 2 === 0 ? 'Парне' : 'Непарне';
    } else {
        return '';
    }
}

// Функція для перевірки, чи є число простим
function isPrime(number) {
    if (number < 2) return false;
    for (let i = 2; i <= Math.sqrt(number); i++) {
        if (number % i === 0) return false;
    }
    return true;
}

// Функція для знаходження перших п'яти простих чисел та їх суми
function sumOfFirstFivePrimes() {
    let primes = [];
    let num = 2;

    while (primes.length < 5) {
        if (isPrime(num)) {
            primes.push(num);
        }
        num++;
    }

    return primes.reduce((sum, prime) => sum + prime, 0);
}

// Функція для підрахунку суми ряду з n чисел виду 1, 11, 111, ...
function sumOfSeries(n) {
    let sum = 0;
    let currentNumber = 0;

    for (let i = 0; i < n; i++) {
        currentNumber = currentNumber * 10 + 1;
        sum += currentNumber;
    }

    return sum;
}

// Приклади використання:
console.log(checkNumber(4));       
console.log(checkNumber(7));    
console.log(checkNumber('a'));     
console.log(sumOfFirstFivePrimes());
console.log(sumOfSeries(5));       

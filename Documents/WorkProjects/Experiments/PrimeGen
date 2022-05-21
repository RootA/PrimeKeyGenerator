# Prime Generation for RSA
import random, re

class KeyGeneratorFromPrimeNumbers:
    def __init__(self):
        # Pre generated primes
        self.first_primes_list = []
        self.p = 1
        self.q = 1
    
    def isprime(self, n):
        return re.compile(r'^1?$|^(11+)\1+$').match('1' * n) is None
    
    def generatePrimeNumbers(self, n):
        self.first_primes_list = [x for x in range(n) if self.isprime(x)]
        return self.first_primes_list
    
    def getRandomNumbers(self):
        p = random.choice(self.first_primes_list)
        q = random.choice(self.first_primes_list)
        print('p: ', p)        
        print('q: ', q)
        self.p = p
        self.q = q
        return [p,q]
    
    # to calculate Euler's
    # Totient Function

    def phi(self, n) :
        result = n   # Initialize result as n

        # Consider all prime factors
        # of n and for every prime
        # factor p, multiply result with (1 - 1 / p)
        while self.p * self.p<= n :

            # Check if p is a prime factor.
            if n % self.p == 0 :

                # If yes, then update n and result
                while n % self.p == 0 :
                    n = n // self.p
                result = result * (1.0 - (1.0 / float(self.p)))
            p = self.p + 1

        # If n has a prime factor
        # greater than sqrt(n)
        # (There can be at-most one
        # such prime factor)
        if n > 1 :
            result = result * (1.0 - (1.0 / float(n)))

        return int(result)

if __name__ == '__main__':
    rangen = 100
    key = KeyGeneratorFromPrimeNumbers()
    key.generatePrimeNumbers(rangen)
    key.getRandomNumbers()
    
    # Driver program to test Eulers function
    for n in range(1, rangen) :
        print("phi(", n, ") = ", key.phi(n))
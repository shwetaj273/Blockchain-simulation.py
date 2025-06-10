# Blockchain-simulation.py
import hashlib  # We'll use Python's built-in hashlib library

class Block:
    def __init__(self, index, timestamp, data, prior_hash=''):
        self.index = index
        self.timestamp = timestamp
        self.data = data
        self.prior_hash = prior_hash
        self.hash = self.create_hash()  # This calls the hashing method
    
    def create_hash(self):
        pass  #
 block_string = f"{self.index}{self.prior_hash}{self.timestamp}{self.data}".encode()
        # Return the hash of this string using SHA-256
        return hashlib.sha256(block_string).hexdigest()

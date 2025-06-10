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
class ErnestoBlockChain:
    def __init__(self):
        self.chain = [self.create_genesis_block()]  # Initialize the chain with the genesis block
    
    def create_genesis_block(self):
        # Create the first block in the blockchain with fixed parameters
        return Block(0, '04/3/1977', 'BlockchainTrainingAlliance.com', '0')
        def get_last_block(self):
        return self.chain[-1] 
        def add_block(self, new_block):
        new_block.prior_hash = self.get_last_block().hash
        new_block.hash = new_block.create_hash()
        self.chain.append(new_block)

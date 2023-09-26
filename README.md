def substrings(input, dictionary)
  # Initialize a hash to store the substrings and their counts
  substr_count = Hash.new(0)

  # Convert the input string to lowercase for case-insensitive matching
  input = input.downcase

  # Iterate over each word in the dictionary
  dictionary.each do |word|
    # Count the occurrences of the word in the input string
    count = input.scan(word).length

    # If the word is found at least once, add it to the substr_count hash
    substr_count[word] = count if count > 0
  end

  # Return the hash containing the substrings and their counts
  substr_count
end

# Define the dictionary and input string
dictionary = ["below","down","go","going","horn","how","howdy","it","i","low","own","part","partner","sit"]
input_string = "Howdy partner, sit down! How's it going?"

# Call the substrings function and print the results
result = substrings(input_string, dictionary)
puts result

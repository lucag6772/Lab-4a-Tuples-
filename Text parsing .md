``` python 

# Lab 6: Text Parsing
# Author: Luka Gerardi
# Objective: Process a story to count words/characters, build word frequency
# histograms using lists and dictionaries, extract emails/phone numbers using regex,
# and manipulate email usernames.


import re
from collections import Counter


# Step 1: Word and Character Count
def word_char_count_list(text):
    words = text.split()  # split story into words
    word_count = len(words)
    char_count = len(text)
    return words, word_count, char_count


# Step 2: Word Frequency
def word_frequency_dict(words):
    freq_dict = {}
    for word in words:
        cleaned_word = word.strip(".,;:!?—[]()\"").lower()
        if cleaned_word:
            freq_dict[cleaned_word] = freq_dict.get(cleaned_word, 0) + 1
    return freq_dict


# Step 3: Extract phone numbers and emails 
def extract_contacts(text):
    phone_pattern = r"\d{1}-\d{3}-\d{3}-\d{4}"
    email_pattern = r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}"

    phone_numbers = re.findall(phone_pattern, text)
    email_addresses = re.findall(email_pattern, text)

    return phone_numbers, email_addresses


# Step 4: Process email usernames
def process_emails(email_addresses):
    usernames = [email.split("@")[0] for email in email_addresses]
    hotmail_addresses = [username + "@hotmail.com" for username in usernames]
    return usernames, hotmail_addresses


# Step 5: Main function
def main():
    story_text = """
    Once on a time and twice on a time, and all times together as ever I heard tell of,
    there was a tiny lassie who would weep all day to have the stars in the sky to play
    with; she wouldn’t have this, and she wouldn’t have that, but it was always the
    stars she would have...
    The story is written by Roger Federer & Serina Williams
    You can connect with the author at [rfederer@tennis.com] and [swilliams@tennis.com]
    Admin contact number: 1-888-111-2222
    """

    # Step 1: Word and character count (list)
    words, word_count, char_count = word_char_count_list(story_text)
    print("Step 1: Using List")
    print(f"Total words: {word_count}")
    print(f"Total characters: {char_count}\n")

    # Step 2: Word frequency (dictionary)
    freq_dict = word_frequency_dict(words)
    print("Step 2: Using Dictionary")
    print(f"Top 10 most common words: {Counter(freq_dict).most_common(10)}\n")

    # Step 3: Regex extraction
    phone_numbers, email_addresses = extract_contacts(story_text)
    print("Step 3: Regex Extraction")
    print("Phone Numbers Found:", phone_numbers)
    print("Email Addresses Found:", email_addresses, "\n")

    # Step 4: Email processing
    usernames, hotmail_addresses = process_emails(email_addresses)
    print("Step 4: Email Processing")
    print("Usernames:", usernames)
    print("Hotmail versions:", hotmail_addresses)


if __name__ == "__main__":
    main()
```

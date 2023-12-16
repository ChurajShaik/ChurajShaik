import tkinter as tk
from tkinter import scrolledtext

class NotesPadApp:
    def __init__(self, root):
        self.root = root
        self.root.title("Notes Pad App")

        # Text area for notes
        self.notes_text = scrolledtext.ScrolledText(root, wrap=tk.WORD, width=40, height=10)
        self.notes_text.pack(pady=10, padx=10)

        # Save Button
        self.save_button = tk.Button(root, text="Save", command=self.save_notes)
        self.save_button.pack(pady=5)

    def save_notes(self):
        notes_content = self.notes_text.get("1.0", tk.END)
        # You can save the notes_content to a file, database, or perform any other action here.
        print("Notes saved:\n", notes_content)

if __name__ == "__main__":
    root = tk.Tk()
    app = NotesPadApp(root)
    root.mainloop()


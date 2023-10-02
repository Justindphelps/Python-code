import os
import shutil

path = 'E:/Documents'
files = os.listdir(path)

for file in files:
    if os.path.isdir(os.path.join(path, file)):
        continue

    filename, extension = os.path.splitext(file)
    extension = extension[1:]

    if not os.path.exists(os.path.join(path, extension)):
        os.makedirs(os.path.join(path, extension))

    shutil.move(os.path.join(path, file), os.path.join(path, extension, file))


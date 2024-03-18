import subprocess
FOLDER_OUT = "/home/edgar/out"
FOLDER_1 = "/home/edgar/folder1"


def checkout_neg(cmd, text):
    result = subprocess.run(cmd, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, encoding='utf-8')
    if (text in result.stdout or text in result.stderr) and result.returncode != 0:
        return True
    else:
        return False


def test_neg1():
    # test1
    assert checkout_neg(f"{FOLDER_OUT}; 7z e arx2bad.7z -o{FOLDER_1} -y", "ERROR"), "test1 FAIL"


def test_neg2():
    # test2
    assert checkout_neg(f"{FOLDER_OUT}; 7z t arx2bad.7z", "ERROR"), "test2 FAIL"

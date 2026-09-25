ssh [user name]@[public IP]-> connects VPS to the machine via user/pass / ssh -i ~/.ssh/[private ssh-key's file name] [user name]@[public IP] -> connects VPS to the machine via SSH Key

ls -> shows all the files in the current directory / ls -l -> shows a list / ls -al shows hidden items

pwd(Print Working Directory) -> shows the current directory

cd [directory address] -> changes current directory(/ is allways the source directory)

cd .. -> moves 1 step back / cd[spacebar ] -> moves to user

touch [file name] -> creates a file (every spacebar creates a new file)

echo -> by using echo u can talk to urself or add stuff to a file eg. echo "stuff stuff" > newfile.txt (can be a non existing file)

nano [file name] -> can edit a file properly (to save the file do: ctrl+x -> y -> enter)

cat [file name] -> to see whats inside the file

shred [file name] -> to make a file unreadable

mkdir [folder name] -> makes a new directory

cp [file name] [./new destination] -> to copy paste a file

mv [file name] [./new destination] -> to move a file

rm [file name] -> to delete a file

rmdir [folder name/] -> to delete a directory & if its not empty use rm -r [folder name/]

ip addr -> get machine ip

expr -> print simple expression

history -> shows all commands executed in order

-fsSL:
-f → خطاهای HTTP را failure حساب کن
-s → خروجی اضافی را ساکت کن
-S → ولی خود خطاها را نشان بده
-L → Redirectها را دنبال کن

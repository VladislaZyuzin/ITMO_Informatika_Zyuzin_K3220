# Лабораторная работа 5
## Введение

На GitHub создал новый репозиторий с именем practice5. В папке на компьютере сохранил его локальную копию:
```
git clone https://github.com/VladislaZyuzin/git-practice-5.git
```
```
bash
```
```
cd giy-practice-5
```
![picture](png1.PNG)
Далее создаю текстовый файл в папке и добавляю в него текст. Завершаю эту часть, внеся изменения в репозиторий с помощью следующих команд:
```
git add example1.txt
git commit -m "File added example1.txt"
git push origin main
```
Создаём ветку и переключаемся на неё:
```
git branch feature-branch
git checkout feature-branch
```
В новую созданную ветку feature-branch добавим старый файл, в котором будет добавлен ещё текст:
```
git add example1.txt
git commit -m "File added 2 example1.txt"
git push origin feature-branch
```
В завершение, переключимся на основную ветку и сольём изменения из ветки feature-branch в основную ветку:
```
git checkout main
git merge feature-branch
git push origin main
```
Таким образом, изменения были успешно слиты в главную ветку.

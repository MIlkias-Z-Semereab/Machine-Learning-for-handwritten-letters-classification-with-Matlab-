# Machine-Learning-for-handwritten-letters-with-Matlab-classification
letter = readtable("M.txt");
letter.X = letter.X*1.5;
letter.Time = (letter.Time - letter.Time(1))/1000
plot(letter.X,letter.Y)
axis equal
dur_m=letter.Time(end)-letter.Time(1)
aratio_m=range(letter.Y)/range(letter.X)

%pre-process j
letter_j = readtable("J.txt");
letter_j.X = letter_j.X*1.5;
letter_j.Time = (letter_j.Time - letter_j.Time(1))/1000
plot(letter_j.X,letter_j.Y)
axis equal

dur_j=letter_j.Time(end)-letter_j.Time(1)
aratio_j=range(letter_j.Y)/range(letter_j.X)

%pre-process v
letter_v = readtable("V.txt");
letter_v.X = letter_v.X*1.5;
letter_v.Time = (letter_v.Time - letter_v.Time(1))/1000
plot(letter_v.X,letter_v.Y)
axis equal

dur_v=letter_v.Time(end)-letter_v.Time(1)
aratio_v=range(letter_v.Y)/range(letter_v.X)

Feature=[dur_m aratio_m;dur_j aratio_j;dur_v aratio_v]

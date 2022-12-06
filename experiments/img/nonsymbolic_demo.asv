%% Nonsymbolic stimuli 

num1 = 10:5:30;
num2 = 10:5:30;

allcombs = allcomb(num1,num2);
allcombs = allcombs(allcombs(:,1)./allcombs(:,2)~=1,:);

list = {};
for i = 1:size(allcombs,1)
    figure('units', 'normalized', 'outerposition', [0 0 .3 .3]) % [0 0 .6 .3]
    plot(rand(allcombs(i,1),1,1), '.', 'MarkerSize', 30, 'Color', 'blue')
    hold on
    plot(rand(allcombs(i,2),1,1), '.', 'MarkerSize', 30, 'Color', 'red')
    axis square
    axis off
    set(gcf,'color','w');
    set(gca,'color','w');

    filename = ['dots', '_', num2str(allcombs(i,1)), '_', num2str(allcombs(i,2)), '.png'];
    if allcombs(i,1) > allcombs(i,2)
       resp = 'f';
    else
       resp = 'j';
    end

    trial = sprintf('%s%s%s%s%s%s%s%s%s%s', '{ stimulus: ', "'", 'img/', filename, "'", ',  correct_response: ', "'", resp, "'", '},');


    list = [list; trial];
    f = gcf;
    exportgraphics(f,filename,'Resolution',100)
    close all
end

writetable(table(list), 'list.csv')

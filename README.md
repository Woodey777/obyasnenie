# шо происходит

создан репозиторий [RPO_lab4](https://github.com/kpaul-sus/RPO_lab4), туда добавлены люди и ветка main закрыта для прямых коммитов 
люди добавляются в настройках репозитория, в cooperators, ветка тоже где-то там закрывается

### этап 0
склонирован репозиторий (git clone https://github.com/kpaul-sus/RPO_lab4.git)
созданы начальные файлы (https://github.com/kpaul-sus/RPO_lab4/tree/5e3c87290be8719686c6b1b86c7ea64d63720b40)
`git add .`
`git commit -m “init project”`

### этап 1
от веки main делается новая [ветка](https://github.com/kpaul-sus/RPO_lab4/tree/feature1) 
`git switch main`
`git checkout -b feature1`
немного [изменяются](https://github.com/kpaul-sus/RPO_lab4/commit/fbbe5fcce9a0f1aca484318771494d6ef64ed4d0) файлы(добавляем feature1)
делаем коммит
`git add .`
`git commit -m “done feature1”`
заходим в проект в github, в ветку main и создаем [pull request](https://github.com/kpaul-sus/RPO_lab4/pull/1) (запрос на добавление изменений в ветку main)
чтобы сделать мердж(объединиение) измененией в ветку main, нужно получить одобрение(approve) от другого участника 
другой участник оставляет [комментарий](https://github.com/kpaul-sus/RPO_lab4/pull/1#discussion_r2062678439) в pullrequest, о том, что нужно исправить. 
после этого создатель fature1 идет снова в код и [исправляет](https://github.com/kpaul-sus/RPO_lab4/pull/1/commits/3414dd97ba4902dbc8e8fd8f2e327ce507c9e231) его. снова делает commit
`git add .`
`git commit -m “fix feature1”`
изменения автоматически появляются в pull req. после этого проверяющий нажимает кнопку approve, и создатель может делать merge
нажимается кнопка squash and merge, чтобы объединить все коммиты из feature1 в один коммит

### этап 2
до мерджа feature1 в main второй участник делает от main другую [ветку](https://github.com/kpaul-sus/RPO_lab4/tree/feature2) 
`git switch main`
`git checkout -b feature2`
точно также добавляет [изменения](https://github.com/kpaul-sus/RPO_lab4/commit/1bfbece7f1bab0cc69d5f63b469ad35aedc9ef29) и коммитит их
создает [pull request](https://github.com/kpaul-sus/RPO_lab4/pull/2) (после мерджа feature1)
из-за того, что у него изменения сделаны до добавления feature1, а мердж он делает в ветку, где они уже есть, получается конфликт
его разрешаем прямо в github(на скрине в отчете есть). нужно удалить ненужные строчки и оставить нужные
после этого получаем approve, как в этапе 1 и делаем merge

### этап 3
еще до мержда этапа 2 (да вот такой вот ДОВОД тут))) создается ветка feature3. туда вносятся изменения и добавляется фича
уже **после** merge предыдущего этапа получается, что века feature3 отстает от main на один шаг
это можно исправить коммандой 
`git rebase main`
она перенесет начало ветки feature3 в самый крайний коммит main (на схеме из отчета видно)
при этом тоже появляются конфликты, которые нужно разрешить
разрешаем и делаем коммит
## profit))
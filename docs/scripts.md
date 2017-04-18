##### [������� ��������](../README.md)

### ������ �� ��������� ��������

`������ ��������` �������������
���������� �������� "������ ��������" ����� ����������� �������� �������� �������������. ����� ������� ����� ������� ��� �������� � ��������
�������� ����� ������.

#### 1. �������� ������ �������� ��������

�������� ������ �������� �������������� �� ���� `�������� ������ -> �������� ����������`,
��� ���������� ������ �������� ��������, ������� ��� �������� � ��������� ����� ����������

�������� ����������� � ������� ����������:
�������, �������, ������������. � �������� ���� ���������� �������� �������������� �� ���� �������� �����.
�������� ���� "������������" ����� ���� ��������.

###### �������� ��������. ���� ��������

![�������� ��������. ���� ��������](../data/create_scenario.png)

�������� ����� �������� ����������. ����� �������� ���������� ��������� � ����������� � ��������������� ����� ������

![�������� ��������. ���� ��������](../data/update_scenario.jpg)

#### 2. ��������������. ����������� ��������� ���������� �������

�� ����, ���������� � ��������� ��������� ��������� �����

###### ��������. �������������� ������

```php
<?php

/**
 * Class definition update migrations scenario actions
 **/
class ws_m_1492519399_sozdanie_veb_formy_obratnoy_svyazi extends \WS\ReduceMigrations\Scenario\ScriptScenario {

    /**
     * Name of scenario
     **/
    static public function name() {
        return "�������� ���-����� �������� �����";
    }

    /**
     * Priority of scenario
     **/
    static public function priority() {
        return "high";
    }

    /**
     * @return string hash
     */
    static public function hash() {
        return "55925bade27806617493ee99588050aca0463073";
    }

    /**
     * @return string is owner name
     */
    static public function owner() {
        return "Igor Pomiluyko";
    }

    /**
     * @return string approximately time
     */
    static public function approximatelyTime() {
        return "2";
    }

    /**
     * Write action by apply scenario. Use method `setData` for save need rollback data
     **/
    public function commit() {
        // my code
    }

    /**
     * Write action by rollback scenario. Use method `getData` for getting commit saved data
     **/
    public function rollback() {
        // my code
    }
}
```


� ��� ������������� ��� ����������� ��� ������:
* `commit` - �������� �������� ���������� ��������
* `rollback` - �������� �������� ������ ��������

������ `getData` � `setData` ������������� ������ � ������ � �� ���������� ��������������, ���������� ��� ���������� ������ ��� ������.

#### 3. ����������

���������� ��������� �������� �������������� ����� ���������� ������ ����������.

###### ���������� ��������� ��������

![���������� ��������� ��������](../data/main.jpg)

������ �� ��������� �������� ����� �������� � ������ ���������.

#### ������ ��� ��������� ������ � ���������� ��������

��� ��������� �������� ���������� ������ (�������) ����������� ����� � ������ ��������� ����� �������� ������.

������ � ��������� �������� ��������� �������:

```php
<?php

$ibBuilder = new \WS\ReduceMigrations\Builder\IblockBuilder();
$ibBuilder->createIblock('type_content', '�������', function (\WS\ReduceMigrations\Builder\Entity\Iblock $iblock) {
    $iblock
        ->siteId('s1')
        ->sort(100)
        ->code('news')
        ->groupId([
           '2' => 'R' 
        ]);
    $iblock
        ->addProperty('�������� �� �������')
        ->code('showOnMain')
        ->typeCheckbox()
        ->addEnum('��');
});

```

�������� �������:

* \WS\ReduceMigrations\Builder\TableBuilder
* \WS\ReduceMigrations\Builder\IblockBuilder
* \WS\ReduceMigrations\Builder\HighLoadBlockBuilder
* \WS\ReduceMigrations\Builder\FormBuilder
* \WS\ReduceMigrations\Builder\EventsBuilder
* \WS\ReduceMigrations\Builder\AgentBuilder

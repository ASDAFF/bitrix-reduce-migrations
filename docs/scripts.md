##### [������� ��������](../README.md)

### ������ �� ��������� ��������

����� ������������ ����������� �������������� �������� �� ������� ��� ��������� ������ (�����) ������� � ���������� ���������, `������ ��������` �������������
���������� �������� "������ ��������" ����� ����������� �������� �������� �������������. ����� ������� ����� ������� ��� �������� � ��������
�������� ����� ������.

#### 1. �������� ������ �������� ��������

�������� ������ �������� �������������� �� ���� `�������� ������ -> �������� ����������`,
��� ���������� ������ �������� �������� � ��������

###### �������� ��������. ���� ��������

![�������� ��������. ���� ��������](../data/create_scenario.png)

�������� ����� �������� ����������. ����� �������� ���������� ��������� � ����������� � ��������������� ����� ������

![�������� ��������. ���� ��������](../data/update_scenario.png)

#### 2. ��������������. ����������� ��������� ���������� �������

�� ����, ���������� � ��������� ��������� ��������� �����

###### ��������. �������������� ������

```php
<?php

/**
 * Class definition update migrations scenario actions
 **/
class ws_m_1458654949_pervoe_migrirovanie_na_platformu extends \WS\ReduceMigrations\ScriptScenario {

    /**
     * Name of scenario
     **/
    static public function name() {
        return "������ ������������ �� ���������";
    }

    /**
     * Description of scenario
     **/
    static public function description() {
        return "";
    }

    /**
     * @return array First element is hash, second is owner name
     */
    public function version() {
        return array("0b293915ef769882aa400eb10cfa2540", "Master");
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

� ������, ���� ������� �������� �������� � ������� � ��������������� ���������� ������ �������� ������������ ������ � ����������� ������ `$this->getReferenceController()` ���
����������� ��� ��������� ��������������� ������� �������� ������� ����� �������, �� ��������� ��� ������ � ����������, ������� ����� ������������� ��������������.

#### 3. ����������

���������� ��������� �������� �������������� ����� ���������� ������ ����������.

###### ���������� ��������� ��������

![���������� ��������� ��������](../data/main.png)

������ �� ��������� �������� ����� �������� � ������ ���������. � ������� ��������� ����� ����������� ������������� ����������.

#### ������ ��� ��������� ������ � ���������� ��������

��� ��������� �������� ���������� ������ (�������) ����������� ����� � ������ ��������� ����� �������� ������.

������ � ��������� �������� ��������� �������:

```php
<?php

$ibBuilder = new \WS\ReduceMigrations\Builder\IblockBuilder();
$ibBuilder->getIblock("������� �������");

$ibBuilder
    ->getSection("������� �������")
    ->setName("������� ��� ����");

// ���������� ��������� � ���� ������
$ibBuilder->commit();
```

�������� �������:

* \WS\ReduceMigrations\Builder\IblockBuilder
* \WS\ReduceMigrations\Builder\HighLoadBlockBuilder
* \WS\ReduceMigrations\Builder\FormBuilder
* \WS\ReduceMigrations\Builder\EventsBuilder
* \WS\ReduceMigrations\Builder\AgentBuilder

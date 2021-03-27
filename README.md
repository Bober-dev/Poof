void del(int n) // n - позиция удаляемого элемента
{
    if ((HEAD != NULL) && (n < size) && (n >= 0)) // если по этому номеру что-то лежит и этот элемент внутри списка
    {
        // Mass - объекты, которые хранятся в списке
        Mass *temp = HEAD, *helping = HEAD;

        for (int i = 0; i < n; i++)
        {
            helping = temp; // предыдущее значение temp
            temp = temp->Next;
        }

        if (temp == HEAD) // если элемент который надо удалить первый
        {
            HEAD = temp->Next;
        }
        else
        {
            helping->Next = temp->Next;
        }
        cout << "Удаляемый элемент: " << *temp;
        free(temp);
        size--; // уменьшаем размер списка
    }
}

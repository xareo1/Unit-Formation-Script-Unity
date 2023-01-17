using UnityEngine;
using System.Collections.Generic;

public class Formation : MonoBehaviour
{
    public GameObject unitPrefab; // prefab for the units in the formation
    public int rows; // number of rows in the formation
    public int columns; // number of columns in the formation
    public float spacing; // distance between units in the formation

    private List<GameObject> units; // list of units in the formation

    void Start()
    {
        units = new List<GameObject>();

        // create the units and position them in the formation
        for (int i = 0; i < rows; i++)
        {
            for (int j = 0; j < columns; j++)
            {
                GameObject unit = Instantiate(unitPrefab);
                unit.transform.position = transform.position + new Vector3(j * spacing, 0, i * spacing);
                units.Add(unit);
            }
        }
    }

    // move the formation to a new position
    public void MoveFormation(Vector3 newPosition)
    {
        transform.position = newPosition;

        // move each unit in the formation to its new position
        for (int i = 0; i < units.Count; i++)
        {
            int row = i / columns;
            int column = i % columns;
            units[i].transform.position = transform.position + new Vector3(column * spacing, 0, row * spacing);
        }
    }
}

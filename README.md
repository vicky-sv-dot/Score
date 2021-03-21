using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class Score : MonoBehaviour
{
  public delegate void ScoringDelegate(int amount);
  public  ScoringDelegate onScoring;

    [SerializeField] public  int score=0;
    [SerializeField] Text scoreText;

    void Start()
    {
        onScoring = AddScore;
      
    }
    void Update()
    {
        scoreText.text = score.ToString();
    }
    void OnTriggerEnter(Collider other)
    {
        onScoring(10);
    }
    public void AddScore(int amount)

    {
       score += amount;
    }
  
}
  

# Linki-kod
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class MenuManager : MonoBehaviour
{
    public Text HighScore;
    public Text Coins;
    public Text soundButtonText;


    private int hs = 0;
    private int coins = 0;

    private void Start()
    {
        if (PlayerPrefs.HasKey("HighScore"))
        {
            hs = PlayerPrefs.GetInt("HighScore");
        }

        if (PlayerPrefs.HasKey("Coins"))
        {
            coins = PlayerPrefs.GetInt("Coins");
        }

        UpdateUI();


    }
    public void UpdateUI()
    {
        HighScore.text = hs.ToString();
        Coins.text = coins.ToString();
        if (SoundManager.instance.GetMuted())
        {
            soundButtonText.text = "TURN ON SOUND";
        }
        else
        {
            soundButtonText.text = "TURN OFF SOUND";
        }
    }
}

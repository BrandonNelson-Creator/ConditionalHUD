//# ConditionalHUD
 //Hud Example showing weapon changes and health status
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConditionalHUD
{
    class Program
    {
        static int health = 100;
        static string healthStatus;
        static int weaponType = 0;
        static string weaponIdentity = "SOP38 Semi Pistol";
        static int Lives = 3;
        static int score = 0;
        static int enemyType = 0;
        static string enemyIdentity = "BedHead";
        //static int enemyPoints = 0;
        
        
        
        
        static void Main(string[] args)
        {
            
            showHud();
            Enemy(2);
            TakeDamage(50);
            showHud();
            heal(25);
            showHud();
            switchWeapon(3);
            showHud();
            switchWeapon(5);
            HighScore(100000);
            showHud();
            heal(25);
            showHud();
            Enemy(3);
            TakeDamage(80);
            showHud();
            Enemy(0);
            TakeDamage(20);
            showHud();
            
            
            Console.ReadKey(true);
        }



        static void showHud()
        {

            healthStatus = HealthStatus(health);
            Console.ForegroundColor = ConsoleColor.Green;
            Console.WriteLine("HUD-------------------------------------------------");
            Console.WriteLine("HighScore: " + score);
            Console.WriteLine("Health: " + health);
            Console.WriteLine("Health Status: " + healthStatus);
            Console.WriteLine("Weapon: " + weaponIdentity);
            Console.WriteLine("Lives: " + Lives);
            Console.WriteLine("----------------------------------------------------");
            Console.ResetColor();
        }
      
        static void TakeDamage(int damage)

        {
            Console.WriteLine("Player is taking " + damage + " damage");
            Console.WriteLine();

            health = health - damage;          
            if (health <= 0)
            {
                health = 0;
                Lives = Lives - 1;
                health = 100;
                Console.WriteLine("YOU DIED");
            }
        }
        static void heal(int HP)
        {
            health = health + HP;
            if (health >= 100)
            {
                health = 100;

            }
            Console.WriteLine("Player picked up " + HP + " health points");
            Console.WriteLine();
        
        }

        static void HighScore(int points)
        {
            score = score + points;
            
            if (points >= 100000)
            {
                Lives = Lives + 1;
            }
            Console.WriteLine("player picked up " + score + " points!");
        }

        static void switchWeapon(int weaponPickup)
        {
            weaponType = weaponPickup;
            if (weaponType == 0)
            {
                weaponIdentity = "SOP38 Semi Pistol";
            }

            if (weaponType == 1)
            {
                weaponIdentity = "M29 Assault Rifle";
            }

            if (weaponType == 2)
            {
                weaponIdentity = "12 Gauge ShotGun"; 
            }

            if (weaponType == 3)
            {
                weaponIdentity = "Double Barrel ShotGun";
            }

            if (weaponType == 4)
            {
                weaponIdentity = "XL2 Lasergun";
            }

            if (weaponType == 5)
            {
                weaponIdentity = "Cannon";
            }

            Console.WriteLine("Player has switched to " + weaponIdentity);
            Console.WriteLine();
        }

        static string HealthStatus(int healthValue)
        {
            health = healthValue;

            if (health >= 75) //&& health <= 100)
            {
                return "Healthy";
            }
            else if (health >= 50) //&& health <= 75)
            {
                return "Hurt";
            }
            else if (health >= 25) //&& health <= 50)
            {
                return "Badly Hurt";
            }

            else if (health >= 1) //&& health <= 25)
            {
                return "Dying";
            }

            else if (health <= 0)
            {
                return "DEAD";
            }
            else 
            { 
                return "Healthy"; 
            }
        }

        //static void Enemypoints(int enemyValue)
        //{
            //enemyPoints = enemyValue = 0;

            

       // }

        static void Enemy(int encounter)
        {
            enemyType = encounter;
            
            if (enemyType == 0)
            {
                enemyIdentity = "BedHead";
            }

            if (enemyType == 1)
            {
                enemyIdentity = "Gnaar";
            }

            if (enemyType == 2)
            {
                enemyIdentity = "Kleer";
            }

            if (enemyType == 3)
            {
                enemyIdentity = "Aludran Reptiloid";
            }

            Console.WriteLine("Player has ran into " + enemyIdentity);
            Console.WriteLine(" ");
                    
        }
        
    }
}

                
            
            

            
            

public class Fighter {
    String name;
    int HP;
    int MP;
    int atk;

    public Fighter(String s, int hp, int mp, int a){
        name = s;
        HP = hp;
        MP = mp;
        atk = a;
    }
    void print_status(){
        System.out.println(String.format("名前:%s HP:%d MP:%d ATK:%d", name, HP, MP, atk));
    }
    void healing(int power) {
        System.out.println(name + "のヒーリング");
        if(MP >= power){
            MP -= power;
            HP += power;
            System.out.println(name + "はHPを" + power + "回復した");
        }
        else {
            System.out.println("MPが足りない");
        }
    }
    void powerup(int power) {
        System.out.println(name + "のパワーアップ");
        if (MP >= power){
            MP -= power;
            atk += power;
            System.out.println(name + "の攻撃力が" + power + "上昇");
        }
        else {
            System.out.println("MPが足りない");
        }
    }
    void attack(Fighter targegt){
        System.out.println(name + "の攻撃！" + targegt.name + "に" + atk + "ダメージ");
        targegt.HP -= atk;
    }
    void superattack(Fighter target, int power){
        if (MP >= power){
            System.out.println(name + "の必殺技" + target.name + "に" + (atk * 3) + "ダメージ");
            target.HP -= (atk * 3);
        }
        else {
            System.out.println("MPが足りない");
        }
    }
}

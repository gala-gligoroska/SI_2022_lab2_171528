# SI_2022_lab2_171528

Gala Gligoroska 171528

2. Control Flow Graph 

      public static List<String> function(List<String> list) {
        if (list.size() <= 0) {   //A
            throw new IllegalArgumentException("List length should be greater than 0"); //B
        }
        int n = list.size();  //C
        int rootOfN = (int) Math.sqrt(n); //C
        if (rootOfN * rootOfN  != n) { //C
            throw new IllegalArgumentException("List length should be a perfect square"); //D
        }
        List<String> numMines = new ArrayList<>(); //E
        for (int i = 0; i < n; i++) { //E1, E2, E3
            if (!list.get(i).equals("#")) { //F
                int num = 0; //G
                if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) || (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ) { //G
                    if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) && (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ){ //H
                        num += 2; //I
                    }
                    else { //J
                        num  += 1; //J
                    }
                }
                if (i - rootOfN >= 0 && list.get(i - rootOfN).equals("#")){ //K
                    num++; //L
                }
                if (i + rootOfN < n && list.get(i + rootOfN).equals("#")){ //M
                    num++; //N
                }
                numMines.add(String.valueOf(num)); //O
            }
            else { //P
                numMines.add(list.get(i)); //P
            }
        }
        return numMines; //Q
    }

 ![image](https://user-images.githubusercontent.com/63419322/171912416-f4ece3a7-eed4-4cb7-b4d2-ea9ee7cd2b41.png)

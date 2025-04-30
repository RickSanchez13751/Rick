import java.util.HashMap;
import java.util.Map;

public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> lookup = new HashMap<>(); // Храним число и его индекс

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i]; // Ищем, какое число нужно к текущему, чтобы получить target

            if (lookup.containsKey(complement)) {
                // Если уже видели нужное число — возвращаем его индекс и текущий
                return new int[] {lookup.get(complement), i};
            }

            // Иначе добавляем текущее число в Map
            lookup.put(nums[i], i);
        }

        // Если пара не найдена — возвращаем пустой массив
        return new int[] {};
    }

    public static void main(String[] args) {
        int[] nums = {1, 7, 11, 2};
        int target = 9;

        int[] result = twoSum(nums, target);
        if (result.length == 2) {
            System.out.println("Индексы: [" + result[0] + ", " + result[1] + "]");
        } else {
            System.out.println("Пара не найдена.");
        }
    }
}
# Rick
Проверка

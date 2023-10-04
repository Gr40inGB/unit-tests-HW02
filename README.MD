
### HomeWork2
```java
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.assertj.core.api.Assertions.assertThat;
import static org.junit.jupiter.api.Assertions.*;

class VehicleTest {
    Car car = new Car("Ford", "Focus", 2003);
    Motorcycle motorcycle = new Motorcycle("Suzuki", "Panthera", 2003);

    @BeforeEach
    void setup() {
        car = new Car("Ford", "Focus", 2003);
        motorcycle = new Motorcycle("Suzuki", "Panthera", 2003);
    }


    @Test
    void carIsVehicleTest() {
        assertTrue(car instanceof Vehicle);
    }

    @Test
    void carHas4WheelTest() {
        assertThat(car.getNumWheels()).isEqualTo(4);
    }

    @Test
    void motorcycleHas2WheelTest() {
        assertThat(motorcycle.getNumWheels()).isEqualTo(2);
    }

    @Test
    void carTestDriveSpeedTest() {
        car.testDrive();
        assertThat(car.getSpeed()).isEqualTo(60);
    }

    @Test
    void motorcycleTestDriveSpeedTest() {
        motorcycle.testDrive();
        assertThat(motorcycle.getSpeed()).isEqualTo(75);
    }

    @Test
    void carParkingTest() {
        car.testDrive();
        car.park();
        assertThat(car.getSpeed()).isZero();
    }

    @Test
    void motorcycleParkingTest() {
        motorcycle.testDrive();
        motorcycle.park();
        assertThat(motorcycle.getSpeed()).isZero();
    }
}
```
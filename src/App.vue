<template>
  <div class="form-box">
    <form action="post">
      <label for="job">Звання</label>
      <input
          type="text"
          class="form__input"
          id="job"
          v-model="job"
      >
      <label for="surname">
        Призвище
      </label>
      <input
          type="text"
          class="form__input"
          id="surname"
          v-model="surname"
      >
      <label for="name">
        Ім'я
      </label>
      <input
          type="text"
          class="form__input"
          id="name"
          v-model="name"
      >
      <label for="father">
        По Батькові
      </label>
      <input
          type="text"
          class="form__input"
          id="father"
          v-model="father"
      >
    </form>

    <form action="post">
      <label for="big">Бат</label>
      <select v-model="big" id="big">
        <option
            value="1"
        >
          1БМП
        </option>
        <option
            value="2"
        >
          2БМП
        </option>
        <option
            value="3"
        >
          3БМП
        </option>
      </select>
      <label for="med">Рота</label>
      <select v-model="med" id="med">
        <option value="1">1РМП</option>
        <option value="2">2РМП</option>
        <option value="3">3РМП</option>
      </select>

      <label for="middle">Взвод</label>
      <select v-model="middle" id="middle">
        <option value="1">1 Взвод</option>
        <option value="2">2 Взвод</option>
        <option value="3">3 Взвод</option>
      </select>

      <label for="small">Відділення</label>
      <select v-model="small" id="small">
        <option value="1">1 Відділення</option>
        <option value="2">2 Відділення</option>
        <option value="3">3 Відділення</option>
      </select>

      <label for="pos">Посада</label>
      <select v-model="pos" id="pos">
        <option value="0">Командир взводу</option>
        <option value="1">Бойовий медик взводу</option>
        <option value="2">Стрілець-снайпер</option>
        <option value="3">Водій</option>
        <option value="4">Командир бойової машини-командир відділення</option>
        <option value="5">Заступник командира бойової машини-навідник-оператор</option>
        <option value="6">Старший стрілець</option>
        <option value="7">Старший механік-водій</option>
        <option value="8">Стрілець-снайпер</option>
        <option value="9">Старший водій-гранатометник</option>
        <option value="10">Старший водій-гранатометник</option>
        <option value="11">Навідник</option>
        <option value="12">Номер обслуги</option>
        <option value="13">Кулеметник</option>
        <option value="14">Стрілець-санітар</option>
        <option value="15">Гранатометник</option>
        <option value="16">Механік-водій</option>
      </select>
    </form>

    <div class="output">
      <p>
        {{ job }} {{ surname.toUpperCase() }} {{ name }} {{ father }}, призначеного наказом
        командира військової частини А2022 (по особовому складу) від 18 листопада
        2022 року №67-РС на посаду {{ jobs[pos].desc.toUpperCase() }} {{ small }} ВІДДІЛЕННЯ МОРСЬКОЇ
        ПІХОТИ {{ middle }} ВЗВОДУ МОРСЬКОЇ ПІХОТИ {{ med }} РОТИ МОРСЬКОЇ ПІХОТИ {{ big }}
        БАТАЛЬЙОНУ МОРСЬКОЇ ПІХОТИ військової частини А4765, який прибув із
        військової частини А1275, з 20 листопада 2022 року зарахувати до списків
        особового складу, на всі види забезпечення, а на котлове забезпечення по нормі
        згідно з каталогом продуктів харчування під час повсякденної діяльності
        (триразове харчування) з 21 листопада 2022 року, і вважати таким, що з 20
        листопада 2020 року прийняв справи та посаду і приступив до виконання
        службових обов’язків за посадою. Встановити тарифний розряд №{{ jobs[pos].tarif }}
        з посадовим окладом в розмірі {{ jobs[pos].po }} гривень на місяць, {{ jobs[pos].vos }}, шпк “{{ jobs[pos].spk }}”.
      </p>
      <p>
        Виплачувати щомісячну премію за особистий внесок у загальні результати
        служби в розмірі {{ jobs[pos].bonus }} посадового окладу, надбавку за особливості проходження
        служби у розмірі 87,8% посадового окладу (з урахуванням коефіценту
        збільшення розміру надбавки) з урахуванням окладу за військовим званням та
        надбавки за вислуги років.
      </p>
      <p>
        Підстава: наказ командира військової частини А2022 (по особовому
        складу) від 18 листопада 2022 року №67-РС, рапорт матроса Юрія Білоуса
        (вх.№203/1080 від 20.11.2022 року), поіменний список командира військової
        частини А1275 №740/33/4545 від 19.11.2022 року.
      </p>
    </div>

  </div>

</template>

<script>
  export default {
    data() {
      return {
        job: '',
        name: '',
        surname: '',
        father: '',
        big: '',
        med: '',
        middle: '',
        small: '',
        pos: '1',
        jobs: [
          {
            tarif: 7,
            po: 3000,
            vos: '878033М',
            spk: 'молодший сержант',
            desc: 'Бойового медика',
            bonus: '291%',
          },
          {
            tarif: 7,
            po: 3000,
            vos: '878033М',
            spk: 'молодший сержант',
            desc: 'Бойового медика',
            bonus: '291%',
          },
          {
            tarif: 4,
            po: 2730,
            vos: '100672М',
            spk: 'матрос',
            desc: 'Стрільця-снайпера',
            bonus: '320%',
          },
          {
            tarif: 5,
            po: 2820,
            vos: '790037М',
            spk: 'матрос',
            desc: 'Водія',
            bonus: '307%',
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант',
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант',
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант',
          },{
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
          {
            tarif: 12,
            po: 3440,
            vos: '0212003',
            spk: 'старший лейтенант'
          },
        ],
      }
    }
  }
</script>

<style>
  form {
    display: inline-block;
    margin-right: 20px;
  }

  select {
    display: block;
    margin-bottom: 20px;
    height: 20px;
    width: 150px;
  }

  option {
    display: block;
    height: 20px;
  }

  .form__input {
    display: block;
    margin-bottom: 20px;
    height: 20px;
  }

  .form-box {
    display: flex;
  }

  .output {
    width: 650px;
    margin: 0 auto;

    border: 1px solid black;
    border-radius: 5px;
    padding: 5px;

    font-family: "Times New Roman",serif;
    font-size: 18.63px;
    text-align: justify;
  }

  p {
    margin-bottom: 0
  }

  p {
    text-indent: 47px;
    margin-top: 0
  }
</style>
